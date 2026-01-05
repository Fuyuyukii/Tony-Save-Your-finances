# Sistema Unificado de Envelopes

## Decisão de Design: Unificação de Metas e Envelopes

**Data:** 2026-01-04

### Contexto

Anteriormente, o sistema tinha duas features separadas:
1. **Sistema de Metas** - para economizar e comprar produtos específicos
2. **Sistema de Envelopes/Reservas** - para separar dinheiro para despesas futuras

### Problema

Ambos os sistemas fazem essencialmente a mesma coisa: **separar virtualmente dinheiro dentro de uma conta para um objetivo específico**. Manter dois sistemas separados resultaria em:
- Duplicação de código
- Complexidade desnecessária
- Confusão para o usuário (qual usar?)
- Manutenção dobrada

### Solução: Sistema Unificado

Criar um único sistema de **Envelopes** com dois tipos:

#### 1. Envelope tipo FUNDO
- Para **reservas contínuas**
- Nunca finaliza automaticamente
- Exemplos:
  - Reserva de emergência
  - IPVA/IPTU
  - Férias
  - Presentes
- Comportamento: Continua acumulando mesmo após atingir a meta

#### 2. Envelope tipo META
- Para **objetivos específicos de compra**
- Finaliza quando atinge 100%
- Pode ter produto vinculado (imagem, URL, preço)
- Gamificação mais forte
- Exemplos:
  - Notebook Gamer
  - Viagem
  - Carro
  - Reforma
- Comportamento: Status muda para COMPLETO ao atingir meta

---

## Conceito Fundamental: Potes Separados

**Envelopes são "potes/cofres separados" com saldo próprio.**

Depositar no envelope = tirar da conta e colocar no pote
Retirar do envelope = tirar do pote e devolver para conta

### Exemplo Prático:

```
CONTAS:
├─ Nubank: R$ 5.000,00
└─ Carteira: R$ 300,00

ENVELOPES (separados):
├─ 🚗 IPVA 2026: R$ 800,00
├─ 💻 Notebook: R$ 2.500,00
└─ 🏥 Emergência: R$ 1.000,00

PATRIMÔNIO TOTAL: R$ 9.600,00
(5.000 + 300 + 800 + 2.500 + 1.000)
```

**Depositar R$ 300 no envelope IPVA:**
- Conta Nubank: R$ 5.000 → R$ 4.700 (-R$ 300)
- Envelope IPVA: R$ 800 → R$ 1.100 (+R$ 300)
- Sistema cria 2 transações (saída da conta + entrada no envelope)

---

## Schema do Banco de Dados

### Modelo Principal: `Envelope`

```prisma
model Envelope {
  id                    String   @id @default(uuid())
  nome                  String
  icone                 String
  cor                   String
  tipo                  EnvelopeType  // FUNDO ou META

  // Valores
  meta_valor            Decimal
  saldo_atual           Decimal  @default(0)
  prazo                 DateTime?

  // Depósito automático
  deposito_automatico   Boolean
  deposito_valor        Decimal?
  deposito_percentual   Decimal?
  deposito_frequencia   FrequenciaDeposito?

  // Campos específicos para META
  produto_nome          String?
  produto_url           String?
  produto_imagem_url    String?
  produto_preco_atual   Decimal?
  alertas_preco         Boolean

  // Status
  status                EnvelopeStatus  // ATIVO, COMPLETO, PAUSADO, ARQUIVADO

  // Relacionamentos
  conta_id              String
  usuario_id            String
  transacoes            EnvelopeTransaction[]
}
```

### Transações do Envelope

```prisma
model EnvelopeTransaction {
  id                    String   @id @default(uuid())
  tipo                  EnvelopeTransactionType  // DEPOSITO ou RETIRADA
  valor                 Decimal
  descricao             String?
  automatico            Boolean  // se foi depósito automático

  envelope_id           String
  transacao_id          String?  // vincula a Transaction real se for retirada
}
```

---

## Funcionalidades Principais

### ✅ Para Ambos os Tipos (FUNDO e META)

- Criar envelope
- Editar envelope
- Excluir envelope
- Depositar no envelope
- Retirar do envelope
- Transferir entre envelopes
- Histórico de movimentações
- Depósito automático recorrente
- Projeção de tempo para atingir meta
- Barra de progresso visual

### 🎯 Específico para META

- Vincular produto (nome, URL, imagem)
- Rastreamento de preço
- Alertas de variação de preço
- Status COMPLETO ao atingir 100%
- Botão "REALIZAR META"
- Gamificação (notificações em 25%, 50%, 75%, 100%)

### 💰 Específico para FUNDO

- Nunca muda para COMPLETO
- Alertas quando saldo cai abaixo da meta
- Indicação de vencimento (ex: IPVA vence em Março)

---

## Regras de Negócio

| ID | Regra |
|----|-------|
| RN-020 | Envelope tem saldo próprio separado da conta (não é virtual) |
| RN-021 | Depositar em envelope retira dinheiro da conta e adiciona no envelope |
| RN-022 | Retirar do envelope remove do envelope e devolve para a conta |
| RN-023 | Não é possível depositar em envelope se saldo da conta for insuficiente |
| RN-024 | Envelope tipo META muda para status COMPLETO quando saldo_atual >= meta_valor |
| RN-025 | Envelope tipo FUNDO nunca muda para status COMPLETO automaticamente |
| RN-026 | Retirada de envelope não pode exceder o saldo atual do envelope |
| RN-027 | Depósito automático só executa se houver saldo na conta suficiente |
| RN-028 | Transferência entre envelopes debita de um e credita no outro simultaneamente |
| RN-029 | Exclusão de envelope devolve o saldo do envelope para a conta vinculada |
| RN-030 | Depositar/retirar gera 2 transações: uma no envelope e outra na conta |

---

## Interface do Usuário

### Dashboard de Envelopes

```
┌────────────────────────────────────────────────────────┐
│  💼 ENVELOPES                                          │
├────────────────────────────────────────────────────────┤
│  RESUMO DO PATRIMÔNIO:                                 │
│  Contas: R$ 5.300,00                                  │
│  Envelopes: R$ 4.300,00                               │
│  Total: R$ 9.600,00                                   │
│                                                        │
│  💰 FUNDOS                                             │
│  ┌────────────────────────────────────────────────┐  │
│  │  🚗 IPVA 2026                                  │  │
│  │  ████████░░ 80% - R$ 800 / R$ 1.000           │  │
│  │  Vence: Março/2026                             │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  ┌────────────────────────────────────────────────┐  │
│  │  🏥 Reserva Emergência                         │  │
│  │  ██████████ 100% - R$ 1.000 / R$ 1.000 ✅     │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  🎯 METAS                                              │
│  ┌────────────────────────────────────────────────┐  │
│  │  💻 Notebook Gamer Dell G15                    │  │
│  │  [Imagem do produto]                            │  │
│  │  ██████░░░░ 50% - R$ 2.500 / R$ 5.000         │  │
│  │  📊 Faltam 3 meses                             │  │
│  │  💡 Guardar R$ 833/mês                         │  │
│  │  🔗 [Ver Produto] [+ Depositar]                │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  [+ Criar Envelope]                                    │
└────────────────────────────────────────────────────────┘
```

### Criar Envelope - Escolha de Tipo

```
┌────────────────────────────────────────┐
│  💼 Criar Envelope                    │
├────────────────────────────────────────┤
│  Que tipo de envelope?                 │
│                                        │
│  ┌──────────────────────────────────┐ │
│  │  💰 FUNDO                        │ │
│  │  Reserva contínua                │ │
│  │  Ex: IPVA, Emergência, Férias   │ │
│  └──────────────────────────────────┘ │
│                                        │
│  ┌──────────────────────────────────┐ │
│  │  🎯 META                         │ │
│  │  Objetivo de compra              │ │
│  │  Ex: Notebook, Viagem, Carro    │ │
│  └──────────────────────────────────┘ │
│                                        │
│  [Cancelar]                            │
└────────────────────────────────────────┘
```

---

## Depósito Automático Recorrente

### Como Configurar:

**Opção 1: Valor Fixo**
```
Envelope: IPVA 2026
Depósito Automático: Ativado
Valor: R$ 200,00
Frequência: Mensal
Dia: 5 (todo dia 5 do mês)
Conta origem: Nubank
```

**Opção 2: Percentual de Receitas Específicas**
```
Envelope: Reserva de Emergência
Depósito Automático: Ativado
Percentual: 10%
Aplicar em: Receitas com categoria "Salário"
Frequência: Quando receber
Conta origem: Nubank
```

**Opção 3: Percentual de Todas Receitas**
```
Envelope: Notebook Gamer
Depósito Automático: Ativado
Percentual: 5%
Aplicar em: Todas as receitas
Conta origem: Nubank
```

### Como Funciona:

1. Sistema monitora receitas na conta
2. Quando detecta receita configurada (ou no dia programado):
   - Calcula valor a transferir
   - Verifica se conta tem saldo suficiente
   - Cria transação de SAÍDA na conta
   - Cria transação de DEPOSITO no envelope
   - Marca como "automático" no histórico

**Exemplo:**
- Recebeu salário de R$ 3.000
- Envelope "Emergência" configurado: 10% do salário
- Sistema transfere automaticamente R$ 300 para envelope

---

## Benefícios da Unificação

1. **Código limpo** - Um único CRUD, uma única lógica
2. **Experiência consistente** - Usuário aprende uma vez
3. **Flexibilidade** - Fácil mudar FUNDO para META e vice-versa
4. **Manutenção** - Bugs corrigidos em um lugar
5. **Performance** - Menos queries, menos modelos
6. **Escalabilidade** - Fácil adicionar novos tipos no futuro

---

## Migração do Planejamento Original

### Antes (Sistema Duplo)

- ❌ FASE 14: Sistema de Metas
- ❌ Seção separada: Sistema de Reservas e Envelopes Virtuais

### Depois (Sistema Unificado)

- ✅ FASE 14: Sistema de Envelopes (Metas e Fundos)
- ✅ Todas as funcionalidades integradas
- ✅ Documentação consolidada

---

## Referências

- [Schema Prisma completo](schema-envelopes.prisma)
- [DESENVOLVIMENTO.md](../DESENVOLVIMENTO.md) - FASE 14 atualizada
- [SSR.md](../SSR.md) - Requisitos RF-100 a RF-121
- [PLANEJAMENTO.md](../PLANEJAMENTO.md) - Detalhamento das features

---

**Decisão aprovada em:** 2026-01-04
**Implementação prevista:** FASE 14 (v2.0)
