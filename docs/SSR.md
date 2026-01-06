# Tony Save Your Finances - System Requirements Specification (SSR)

## 1. Introdução

### 1.1 Propósito
Este documento especifica os requisitos do sistema Tony Save Your Finances, um aplicativo de controle financeiro pessoal multiplataforma (web e mobile).

### 1.2 Escopo
O sistema permite ao usuário controlar suas finanças pessoais, registrando receitas e despesas, categorizando transações, gerenciando contas bancárias e visualizando relatórios financeiros.

### 1.3 Definições e Abreviações
- **Transação**: Qualquer movimentação financeira (receita ou despesa)
- **Conta**: Conta bancária, carteira digital ou dinheiro físico
- **Categoria**: Classificação de transações (ex: Alimentação, Transporte)
- **Recorrência**: Transação que se repete periodicamente

---

## 2. Descrição Geral

### 2.1 Perspectiva do Produto
Sistema standalone que funciona em:
- Navegadores web (desktop e mobile)
- Aplicativo nativo (iOS e Android)

### 2.2 Funções do Produto
1. Gestão de transações (CRUD)
2. Gestão de contas/carteiras
3. Categorização de gastos
4. Dashboard financeiro
5. Relatórios e gráficos
6. Orçamento por categoria
7. Captura automática de notificações bancárias (mobile)
8. Gestão de dívidas e empréstimos
9. Transações recorrentes

### 2.3 Usuários
- **Usuário final**: Pessoa física que deseja controlar suas finanças pessoais
- **Perfil**: Jovens e adultos com smartphone e/ou acesso a computador

### 2.4 Restrições
- Requer conexão com internet para sincronização
- Dados financeiros sensíveis exigem autenticação
- Captura de notificações disponível apenas no Android

---

## 3. Requisitos Funcionais

### 3.1 Autenticação e Autorização

| ID | Requisito | Prioridade |
|----|-----------|------------|
| RF-001 | O sistema deve permitir cadastro com email e senha | Alta |
| RF-002 | O sistema deve permitir login com email e senha | Alta |
| RF-003 | O sistema deve permitir autenticação biométrica no mobile | Média |
| RF-004 | O sistema deve permitir recuperação de senha por email | Alta |
| RF-005 | O sistema deve manter sessão ativa por 30 dias | Média |

### 3.2 Gestão de Contas

| ID | Requisito | Prioridade |
|----|-----------|------------|
| RF-010 | O sistema deve permitir criar conta com nome, tipo e saldo inicial | Alta |
| RF-011 | O sistema deve permitir editar dados da conta | Alta |
| RF-012 | O sistema deve permitir excluir conta (soft delete) | Alta |
| RF-013 | O sistema deve exibir saldo atual de cada conta | Alta |
| RF-014 | O sistema deve exibir saldo total consolidado | Alta |
| RF-015 | O sistema deve suportar tipos: Conta Corrente, Poupança, Carteira Digital, Dinheiro | Alta |
| RF-016 | No dashboard, clicar no card "Minhas Contas" deve levar à tela de lista de contas | Alta |
| RF-017 | No dashboard, clicar em uma conta específica dentro do card deve levar à tela de detalhes daquela conta | Alta |
| RF-018 | A tela de detalhes da conta deve exibir dados específicos da conta clicada (nome, tipo, emoji, cores, saldos) | Alta |
| RF-019 | A tela de detalhes deve adaptar cor do header conforme a conta (roxo para Nubank, laranja para Inter, verde para Dinheiro) | Alta |

### 3.3 Gestão de Categorias

| ID | Requisito | Prioridade |
|----|-----------|------------|
| RF-020 | O sistema deve fornecer categorias padrão (Alimentação, Transporte, etc.) | Alta |
| RF-021 | O sistema deve permitir criar categorias personalizadas | Média |
| RF-022 | O sistema deve permitir definir ícone e cor para categorias | Baixa |
| RF-023 | O sistema deve permitir subcategorias | Baixa |
| RF-024 | O sistema deve separar categorias de receita e despesa | Alta |
| RF-025 | O sistema deve permitir editar categorias padrão (nome, ícone, cor) | Média |
| RF-026 | O sistema deve ter tela dedicada para gerenciamento de categorias (CRUD) | Alta |
| RF-027 | A seleção de categorias deve ser visualmente consistente em toda aplicação | Alta |

### 3.4 Gestão de Transações

| ID | Requisito | Prioridade |
|----|-----------|------------|
| RF-030 | O sistema deve permitir criar transação com: valor, descrição, data, categoria, conta | Alta |
| RF-031 | O sistema deve permitir editar transação | Alta |
| RF-032 | O sistema deve permitir excluir transação | Alta |
| RF-033 | O sistema deve atualizar saldo da conta automaticamente | Alta |
| RF-034 | O sistema deve permitir anexar comprovante (imagem/PDF) | Baixa |
| RF-035 | O sistema deve permitir adicionar tags/etiquetas | Baixa |
| RF-036 | O sistema deve permitir filtrar por período, categoria, conta | Alta |
| RF-037 | O sistema deve permitir buscar por descrição | Média |

### 3.5 Transações Pendentes (Captura Automática)

| ID | Requisito | Prioridade |
|----|-----------|------------|
| RF-040 | O sistema deve capturar notificações de apps bancários (Android) | Média |
| RF-041 | O sistema deve extrair valor e estabelecimento da notificação | Média |
| RF-042 | O sistema deve criar transação pendente automaticamente | Média |
| RF-043 | O sistema deve exibir fila de transações pendentes para categorização | Média |
| RF-044 | O sistema deve destacar visualmente transações pendentes | Média |

### 3.6 Transações Recorrentes

| ID | Requisito | Prioridade |
|----|-----------|------------|
| RF-050 | O sistema deve permitir criar transação recorrente | Média |
| RF-051 | O sistema deve suportar frequências: diária, semanal, quinzenal, mensal, trimestral, anual | Média |
| RF-052 | O sistema deve permitir definir dia específico (ex: dia 5 do mês) | Média |
| RF-053 | O sistema deve criar transações automaticamente na data | Média |
| RF-054 | O sistema deve permitir pausar/cancelar recorrência | Média |
| RF-055 | O sistema deve permitir definir dia útil específico (ex: 5º dia útil) | Média |
| RF-056 | O sistema deve suportar opções especiais: primeiro/último dia do mês, primeiro/último dia útil | Média |
| RF-057 | O sistema deve permitir marcar recorrência como "valor variável" | Média |
| RF-058 | O sistema deve solicitar confirmação do valor antes de lançar transação com valor variável | Média |
| RF-059 | O sistema deve permitir configurar alertas de lembrete (X dias antes) | Média |
| RF-05A | O sistema deve permitir escolher entre lançamento automático ou apenas notificação | Média |
| RF-05B | O sistema deve permitir definir data de término para recorrência | Baixa |
| RF-05C | O sistema deve exibir preview do próximo lançamento ao configurar recorrência | Baixa |

### 3.7 Dashboard

| ID | Requisito | Prioridade |
|----|-----------|------------|
| RF-060 | O sistema deve exibir saldo total consolidado | Alta |
| RF-061 | O sistema deve exibir resumo do mês (receitas x despesas) | Alta |
| RF-062 | O sistema deve exibir gráfico de gastos por categoria | Alta |
| RF-063 | O sistema deve exibir últimas transações | Alta |
| RF-064 | O sistema deve exibir alertas de orçamento | Média |
| RF-065 | O sistema deve exibir contador de transações pendentes | Média |

### 3.8 Orçamento

| ID | Requisito | Prioridade |
|----|-----------|------------|
| RF-070 | O sistema deve permitir definir limite mensal por categoria | Média |
| RF-071 | O sistema deve exibir progresso de gasto vs limite | Média |
| RF-072 | O sistema deve alertar quando atingir 80% do limite | Média |
| RF-073 | O sistema deve alertar quando estourar limite | Média |
| RF-074 | O sistema deve sugerir divisão baseada em regra 50-30-20 | Baixa |

### 3.9 Gestão de Dívidas

| ID | Requisito | Prioridade |
|----|-----------|------------|
| RF-080 | O sistema deve permitir registrar dívida a pagar | Média |
| RF-081 | O sistema deve permitir registrar empréstimo a receber | Média |
| RF-082 | O sistema deve permitir atribuir pessoa/entidade | Média |
| RF-083 | O sistema deve permitir armazenar dados de pagamento (PIX, boleto) | Média |
| RF-084 | O sistema deve permitir definir prazo/vencimento | Média |
| RF-085 | O sistema deve vincular transação ao pagamento de dívida | Média |

### 3.10 Envelopes (Metas e Fundos)

| ID | Requisito | Prioridade |
|----|-----------|------------|
| RF-100 | O sistema deve permitir criar envelope do tipo FUNDO ou META | Média |
| RF-101 | O sistema deve permitir editar envelope | Média |
| RF-102 | O sistema deve permitir excluir envelope | Média |
| RF-103 | O sistema deve vincular envelope a uma conta específica | Alta |
| RF-104 | O sistema deve permitir depositar valor no envelope | Alta |
| RF-105 | O sistema deve permitir retirar valor do envelope | Alta |
| RF-106 | O sistema deve calcular saldo disponível = saldo real - soma de envelopes | Alta |
| RF-107 | O sistema deve alertar ao tentar gastar dinheiro reservado em envelopes | Média |
| RF-108 | O sistema deve exibir progresso visual do envelope (% atingido) | Alta |
| RF-109 | O sistema deve permitir transferir saldo entre envelopes | Média |
| RF-110 | O sistema deve manter histórico de depósitos e retiradas do envelope | Média |
| RF-111 | O sistema deve suportar depósito automático recorrente | Média |
| RF-112 | O sistema deve permitir configurar valor fixo ou percentual para depósito | Média |
| RF-113 | O sistema deve suportar frequências: diária, semanal, quinzenal, mensal | Média |
| RF-114 | Envelope tipo META deve permitir vincular produto (nome, link de compra) | Baixa |
| RF-115 | Envelope tipo META deve rastrear preço do produto automaticamente a partir do link | Baixa |
| RF-116 | O sistema deve alertar quando preço do produto mudar | Baixa |
| RF-126 | O sistema deve buscar promoções automaticamente para produtos vinculados a metas | Baixa |
| RF-127 | O sistema deve notificar quando encontrar promoção para produto de uma meta | Baixa |
| RF-117 | Envelope tipo META deve mudar status para COMPLETO ao atingir 100% | Média |
| RF-118 | Envelope tipo FUNDO não deve finalizar automaticamente | Alta |
| RF-119 | O sistema deve calcular projeção de tempo para atingir meta | Média |
| RF-120 | O sistema deve sugerir valor mensal necessário para atingir meta no prazo | Média |
| RF-121 | O sistema deve notificar progresso em 25%, 50%, 75% e 100% (tipo META) | Baixa |
| RF-122 | O sistema deve buscar automaticamente a taxa CDI diária via API do Banco Central | Média |
| RF-123 | O sistema deve calcular e aplicar rendimento automaticamente aos envelopes | Alta |
| RF-124 | O sistema deve suportar diferentes tipos de rendimento (CDI, Poupança, Taxa Fixa) | Média |
| RF-125 | O sistema deve armazenar histórico de rendimentos aplicados | Média |

### 3.11 Relatórios

| ID | Requisito | Prioridade |
|----|-----------|------------|
| RF-090 | O sistema deve gerar relatório mensal | Média |
| RF-091 | O sistema deve permitir comparar períodos | Baixa |
| RF-092 | O sistema deve exportar dados em CSV/PDF | Baixa |

---

## 4. Requisitos Não-Funcionais

### 4.1 Desempenho

| ID | Requisito |
|----|-----------|
| RNF-001 | O tempo de resposta das APIs deve ser < 500ms para 95% das requisições |
| RNF-002 | O dashboard deve carregar em < 2 segundos |
| RNF-003 | O sistema deve suportar 1000 usuários simultâneos |

### 4.2 Segurança

| ID | Requisito |
|----|-----------|
| RNF-010 | Senhas devem ser armazenadas com hash bcrypt |
| RNF-011 | Comunicação deve ser via HTTPS |
| RNF-012 | Tokens JWT devem expirar em 7 dias |
| RNF-013 | Dados sensíveis devem ser criptografados em repouso |
| RNF-014 | O sistema deve implementar rate limiting |

### 4.3 Usabilidade

| ID | Requisito |
|----|-----------|
| RNF-020 | Interface deve ser responsiva (mobile-first) |
| RNF-021 | Ações principais devem exigir máximo 3 cliques |
| RNF-022 | Feedback visual para todas as ações do usuário |
| RNF-023 | Suporte a tema claro e escuro |

### 4.4 Disponibilidade

| ID | Requisito |
|----|-----------|
| RNF-030 | Disponibilidade de 99.5% (exceto manutenções programadas) |
| RNF-031 | Backup diário dos dados |
| RNF-032 | Recuperação de desastres em < 4 horas |

### 4.5 Compatibilidade

| ID | Requisito |
|----|-----------|
| RNF-040 | Web: Chrome, Firefox, Safari, Edge (últimas 2 versões) |
| RNF-041 | Mobile: iOS 14+ e Android 10+ |
| RNF-042 | PWA com funcionalidades offline básicas |

---

## 5. Regras de Negócio

| ID | Regra |
|----|-------|
| RN-001 | Transação de despesa deve decrementar saldo da conta |
| RN-002 | Transação de receita deve incrementar saldo da conta |
| RN-003 | Exclusão de transação deve reverter o impacto no saldo |
| RN-004 | Edição de valor deve recalcular saldo corretamente |
| RN-005 | Conta não pode ter saldo negativo (exceto se configurado) |
| RN-006 | Categorias padrão e personalizadas podem ser editadas e excluídas |
| RN-011 | Categorias padrão podem ter nome, ícone e cor editados pelo usuário |
| RN-012 | Categorias padrão e personalizadas funcionam de forma idêntica (mesmas operações disponíveis) |
| RN-013 | A interface de seleção de categorias deve ser consistente em todos os modais (criar e editar transação) |
| RN-007 | Transação pendente não afeta saldo até ser confirmada |
| RN-008 | Recorrência gera transação mesmo se usuário não confirmar |
| RN-009 | Dívida quitada deve criar transação vinculada |
| RN-010 | Transferência entre contas gera 2 transações (saída + entrada) |
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
| RN-031 | Rendimento é aplicado diariamente baseado no tipo configurado (CDI, Poupança, Taxa Fixa) |
| RN-032 | Rendimento de caixinha é 100% atribuído ao envelope |
| RN-033 | Rendimento de conta corrente é proporcional ao valor do envelope sobre o total da conta |
| RN-034 | Sistema busca CDI automaticamente do Banco Central diariamente |
| RN-035 | Rendimento é calculado pro-rata baseado em dias úteis |
| RN-036 | Clicar no card "Minhas Contas" no dashboard redireciona para lista de contas (contas.html) |
| RN-037 | Clicar em conta específica no dashboard redireciona para detalhes da conta (conta-detalhes.html?conta=ID) |
| RN-038 | Tela de detalhes deve carregar dados específicos da conta baseado no parâmetro URL |
| RN-039 | Cada conta possui identificação visual própria (cor do header, emoji, labels) |
| RN-040 | Navegação para detalhes de conta usa event.stopPropagation() para evitar conflito com clique no card pai |
| RN-041 | Modal de depósito/retirada deve exibir a conta vinculada ao envelope específico |
| RN-042 | O saldo disponível para depósito é sempre da conta vinculada ao envelope |
| RN-043 | Envelope tipo META com produto vinculado deve exibir botão para acessar o site de origem do produto |
| RN-044 | Transação recorrente com "valor variável" deve solicitar confirmação do valor antes do lançamento automático |
| RN-045 | Dia útil ignora sábados, domingos e feriados nacionais |
| RN-046 | Se dia específico não existe no mês (ex: dia 31 em fevereiro), usa último dia do mês |
| RN-047 | Lançamento automático cria transação na data; lançamento manual apenas envia notificação/lembrete |
| RN-048 | Preview do próximo lançamento deve atualizar dinamicamente conforme configuração de frequência |

---

## 6. Casos de Uso Principais

### UC-001: Registrar Despesa
**Ator**: Usuário
**Fluxo Principal**:
1. Usuário acessa tela de nova transação
2. Usuário seleciona tipo "Despesa"
3. Usuário informa valor, descrição, data
4. Usuário seleciona categoria e conta
5. Sistema valida dados
6. Sistema cria transação
7. Sistema atualiza saldo da conta
8. Sistema confirma operação

### UC-002: Categorizar Transação Pendente
**Ator**: Usuário
**Fluxo Principal**:
1. Sistema exibe notificação de transação pendente
2. Usuário acessa fila de pendentes
3. Usuário seleciona transação
4. Usuário confirma/edita dados
5. Usuário seleciona categoria
6. Sistema atualiza transação
7. Sistema remove da fila de pendentes

### UC-003: Visualizar Dashboard
**Ator**: Usuário
**Fluxo Principal**:
1. Usuário acessa aplicativo
2. Sistema carrega dados do mês atual
3. Sistema exibe saldo consolidado
4. Sistema exibe resumo receitas x despesas
5. Sistema exibe gráfico por categoria
6. Sistema exibe transações recentes
7. Sistema exibe alertas (se houver)

### UC-004: Criar Envelope de Meta
**Ator**: Usuário
**Fluxo Principal**:
1. Usuário acessa tela de envelopes
2. Usuário clica em "Criar Envelope"
3. Usuário seleciona tipo "META"
4. Usuário informa nome, meta de valor, prazo
5. Usuário opcionalmente adiciona produto (nome, URL, imagem)
6. Usuário configura depósito automático (opcional)
7. Usuário seleciona conta vinculada
8. Sistema valida dados
9. Sistema cria envelope
10. Sistema exibe confirmação

### UC-005: Depositar em Envelope
**Ator**: Usuário
**Fluxo Principal**:
1. Usuário acessa detalhes do envelope
2. Usuário clica em "Depositar"
3. Usuário informa valor a depositar
4. Sistema valida se conta tem saldo suficiente
5. Sistema cria Transaction de SAÍDA na conta vinculada (-valor)
6. Sistema cria EnvelopeTransaction de DEPOSITO (+valor)
7. Sistema atualiza saldo da conta (diminui)
8. Sistema atualiza saldo_atual do envelope (aumenta)
9. Sistema exibe novo progresso (%)
10. Sistema verifica marcos (25%, 50%, 75%, 100%)
11. Sistema exibe notificação se atingiu marco

**Fluxo Alternativo 4a**: Saldo da conta insuficiente
- Sistema exibe mensagem de erro
- Sistema mostra saldo atual da conta
- Sistema sugere valor máximo disponível
- Retorna ao passo 3

### UC-006: Retirar de Envelope
**Ator**: Usuário
**Fluxo Principal**:
1. Usuário acessa detalhes do envelope
2. Usuário clica em "Retirar"
3. Usuário informa valor a retirar e motivo
4. Sistema valida se envelope tem saldo suficiente
5. Sistema cria EnvelopeTransaction de RETIRADA (-valor)
6. Sistema cria Transaction de ENTRADA na conta vinculada (+valor)
7. Sistema atualiza saldo_atual do envelope (diminui)
8. Sistema atualiza saldo da conta (aumenta)
9. Sistema exibe confirmação

**Fluxo Alternativo 4a**: Saldo do envelope insuficiente
- Sistema exibe mensagem de erro
- Sistema mostra saldo atual do envelope
- Retorna ao passo 3

### UC-007: Navegar para Detalhes de Conta
**Ator**: Usuário
**Fluxo Principal**:
1. Usuário acessa o dashboard
2. Usuário visualiza o card "Minhas Contas" com lista de contas
3. Usuário clica em uma conta específica (ex: Nubank, Inter, Dinheiro)
4. Sistema redireciona para conta-detalhes.html?conta=ID
5. Sistema lê parâmetro da URL (conta=nubank, conta=inter, etc.)
6. Sistema carrega dados específicos da conta do objeto contasData
7. Sistema atualiza título da página com nome da conta
8. Sistema atualiza header com cor, emoji e nome específicos da conta
9. Sistema exibe saldo total, disponível e reservado da conta
10. Sistema exibe quantidade de envelopes vinculados
11. Sistema exibe abas: Envelopes, Transações, Configurações

**Fluxo Alternativo 3a**: Usuário clica no card "Minhas Contas" (área vazia)
- Sistema redireciona para contas.html (lista de todas as contas)
- Fim do fluxo

**Fluxo Alternativo 5a**: Parâmetro de conta inválido ou ausente
- Sistema mantém dados padrão (Nubank)
- Continua fluxo normal

---

## 7. Integrações

| Sistema | Tipo | Descrição |
|---------|------|-----------|
| Firebase (FCM) | Push Notifications | Envio de notificações para mobile |
| Notification Listener | Android API | Captura de notificações bancárias |
| Câmera | Device API | Captura de comprovantes/notas |

---

## 8. Glossário

| Termo | Definição |
|-------|-----------|
| Transação | Movimentação financeira de entrada (receita) ou saída (despesa) |
| Conta | Local onde o dinheiro está armazenado (banco, carteira, etc.) |
| Categoria | Classificação do tipo de gasto ou receita |
| Recorrência | Transação que se repete em intervalos definidos |
| Pendente | Transação capturada automaticamente aguardando categorização |
| Saldo | Valor disponível em uma conta |
| Envelope | Pote/cofre separado com saldo próprio para objetivos específicos |
| Envelope FUNDO | Reserva contínua para despesas futuras (IPVA, emergência, etc.) |
| Envelope META | Economia para compra/objetivo específico que finaliza ao atingir 100% |
| Depositar em Envelope | Transferir dinheiro da conta para o envelope (diminui conta, aumenta envelope) |
| Retirar do Envelope | Transferir dinheiro do envelope de volta para a conta (diminui envelope, aumenta conta) |

---

## 9. Histórico de Revisões

| Versão | Data | Descrição | Autor |
|--------|------|-----------|-------|
| 1.0 | 2024-01-02 | Versão inicial | - |
| 1.1 | 2026-01-02 | Adicionados requisitos RF-025 a RF-027 e RN-011 a RN-013 (gestão de categorias) | - |
| 1.2 | 2026-01-02 | Atualizado RN-006: categorias padrão agora podem ser excluídas | - |
| 1.3 | 2026-01-04 | Adicionado sistema de Envelopes: RF-100 a RF-121, RN-020 a RN-030, UC-004 a UC-006, glossário atualizado | - |
| 1.4 | 2026-01-05 | Adicionados requisitos RF-122 a RF-125 (rendimento automático) e RN-031 a RN-035 (regras de rendimento) | - |
| 1.5 | 2026-01-06 | Atualizado RF-114 (link de compra ao invés de imagem), adicionados RF-126 e RF-127 (busca de promoções) | - |
| 1.6 | 2026-01-06 | Adicionados RN-041 e RN-042 (modal depósito/retirada exibe conta vinculada ao envelope) | - |
| 1.7 | 2026-01-06 | Adicionada RN-043 (botão para acessar site de origem do produto vinculado em metas) | - |
| 1.8 | 2026-01-06 | Expandido sistema de recorrências: RF-055 a RF-05C (dia útil, valor variável, alertas, lançamento automático), RN-044 a RN-048 | - |

---

## 10. Notas para Manutenção da Documentação

> **IMPORTANTE:** Este documento deve ser atualizado sempre que novas regras de negócio ou requisitos forem definidos durante o desenvolvimento.
>
> Ao definir uma nova funcionalidade ou regra, adicionar:
> - Novo requisito funcional (RF-XXX) na seção apropriada
> - Nova regra de negócio (RN-XXX) se aplicável
> - Atualizar o histórico de revisões
>
> Manter sincronizado com: DESENVOLVIMENTO.md e PLANEJAMENTO.md
