# Tony Save Your Finances - Plano de Desenvolvimento

## Filosofia de Desenvolvimento

**MVP First** - Construir o mínimo necessário para um sistema financeiro funcional, depois expandir.

### O que é essencial para um app de finanças?
1. ✅ Registrar receitas e despesas
2. ✅ Saber quanto tem em cada conta
3. ✅ Ver para onde o dinheiro está indo (categorias)
4. ✅ Acompanhar se está gastando mais do que ganha

### Fases de Entrega

| Marco | Descrição | Funciona como app de finanças? |
|-------|-----------|-------------------------------|
| **MVP** | CRUD de transações + contas + categorias | ✅ Sim, básico |
| **v1.0** | + Dashboard + Gráficos + Orçamento | ✅ Sim, completo |
| **v1.5** | + Mobile + Sincronização | ✅ Sim, multiplataforma |
| **v2.0** | + Recorrências + Dívidas + Cartões | ✅ Sim, avançado |
| **v3.0** | + Captura automática + ML + OCR | ✅ Sim, inteligente |

---

## Stack de Tecnologias (DEFINIDA)

| Área | Tecnologia | Motivo |
|------|------------|--------|
| **Backend** | NestJS + Fastify + TypeScript | Arquitetura escalável, mais rápido que Express |
| **ORM** | Prisma | Tipagem end-to-end, migrations fáceis |
| **Banco de Dados** | PostgreSQL | ACID para dados financeiros |
| **Frontend Web** | React + Vite + TypeScript | Ecossistema grande, compartilha com mobile |
| **Mobile** | React Native + Expo + Expo Router | Compartilha código com web, builds simplificados |
| **Estilização** | Tailwind + NativeWind + CVA | Funciona web/mobile, componentes próprios |
| **Gráficos** | Recharts | Leve, boa documentação |
| **Push Notifications** | Firebase (FCM) | Grátis, integração nativa com Expo |
| **Deploy Backend** | Railway | Simples, barato, escala bem |
| **Deploy Frontend** | Vercel | Deploy automático, grátis |
| **Deploy Banco** | Neon | PostgreSQL serverless, grátis generoso |

### Arquitetura Visual

```
┌─────────────────────────────────────────────────────────┐
│                      FRONTEND                           │
├─────────────────────────┬───────────────────────────────┤
│      Web (React)        │    Mobile (React Native)      │
│      + Vite             │    + Expo + Expo Router       │
│      + TypeScript       │    + TypeScript               │
├─────────────────────────┴───────────────────────────────┤
│           Tailwind + NativeWind + CVA                   │
│              (Componentes próprios)                     │
└─────────────────────────────────────────────────────────┘
                          │
                          ▼
┌─────────────────────────────────────────────────────────┐
│                      BACKEND                            │
│               NestJS + Fastify + TypeScript             │
│                       Prisma                            │
└─────────────────────────────────────────────────────────┘
                          │
                          ▼
┌─────────────────────────────────────────────────────────┐
│                   BANCO DE DADOS                        │
│                    PostgreSQL                           │
│                   (Host: Neon)                          │
└─────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────┐
│                     SERVIÇOS                            │
├─────────────────────────┬───────────────────────────────┤
│   Push: Firebase (FCM)  │   Deploy: Railway + Vercel    │
└─────────────────────────┴───────────────────────────────┘
```

---

## Testes e Documentação

### Estratégia de Testes

| Camada | Ferramenta | Tipo de Teste |
|--------|------------|---------------|
| **Backend** | Jest + Supertest | Unitários + E2E (endpoints) |
| **Frontend Web** | Vitest + Testing Library | Unitários + Integração (componentes) |
| **Frontend Web** | Playwright | E2E (fluxos completos) |
| **Mobile** | Jest + React Native Testing Library | Unitários + Integração |
| **Mobile** | Detox | E2E (fluxos no dispositivo) |

### Cobertura Mínima

| Área | Cobertura Alvo |
|------|----------------|
| Backend (services) | 80% |
| Backend (controllers) | 70% |
| Frontend (componentes críticos) | 70% |
| Fluxos E2E | Todos os happy paths |

### O que Testar

**Backend:**
- [ ] Testes unitários para services (lógica de negócio)
- [ ] Testes E2E para cada endpoint (request/response)
- [ ] Testes de autenticação e autorização
- [ ] Testes de validação de dados (DTOs)
- [ ] Testes de regras de negócio (saldo, transferências)

**Frontend Web:**
- [ ] Testes de componentes isolados (Button, Input, Card)
- [ ] Testes de formulários (validação, submit)
- [ ] Testes de integração (páginas com API mockada)
- [ ] Testes E2E dos fluxos críticos:
  - Login/Registro
  - CRUD de transações
  - Dashboard carregando dados

**Mobile:**
- [ ] Testes de componentes nativos
- [ ] Testes de navegação
- [ ] Testes E2E dos mesmos fluxos do web

### Documentação de API

| Ferramenta | Uso |
|------------|-----|
| **@nestjs/swagger** | Geração automática de OpenAPI/Swagger |
| **Swagger UI** | Interface visual para testar endpoints |

**Configuração:**
- Decorators em todos os DTOs (`@ApiProperty`)
- Decorators em controllers (`@ApiTags`, `@ApiOperation`, `@ApiResponse`)
- Endpoint `/api/docs` com Swagger UI
- Exportação do JSON OpenAPI para integrações

**Exemplo de documentação esperada:**
```typescript
@ApiTags('transactions')
@Controller('transactions')
export class TransactionsController {
  @Post()
  @ApiOperation({ summary: 'Criar nova transação' })
  @ApiResponse({ status: 201, description: 'Transação criada' })
  @ApiResponse({ status: 400, description: 'Dados inválidos' })
  create(@Body() dto: CreateTransactionDto) {}
}
```

### Scripts de Teste

```bash
# Backend
pnpm --filter api test          # Testes unitários
pnpm --filter api test:e2e      # Testes E2E
pnpm --filter api test:cov      # Cobertura

# Frontend Web
pnpm --filter web test          # Testes unitários/integração
pnpm --filter web test:e2e      # Playwright E2E

# Mobile
pnpm --filter mobile test       # Testes unitários
pnpm --filter mobile test:e2e   # Detox E2E
```

### CI/CD - Testes Automatizados

- [ ] GitHub Actions rodando testes em cada PR
- [ ] Bloquear merge se testes falharem
- [ ] Relatório de cobertura em PRs
- [ ] Testes E2E em ambiente de staging antes de deploy

---
---

# 🎯 MVP - Sistema Financeiro Funcional

> **Objetivo:** Usuário consegue registrar transações, ver saldo das contas e acompanhar para onde o dinheiro vai.

---

## FASE 1 - Setup e Infraestrutura Base
**Complexidade:** ⭐ Simples | **Resultado:** Projeto configurado e rodando

### 1.1 Backend - Setup
- [ ] Inicializar repositório Git (monorepo)
- [ ] Criar projeto NestJS com Fastify adapter
- [ ] Configurar Prisma
- [ ] Configurar PostgreSQL local (Docker)
- [ ] Configurar ESLint + Prettier
- [ ] Configurar variáveis de ambiente (.env)
- [ ] Testar: API rodando em localhost

### 1.2 Frontend - Setup
- [ ] Criar projeto React com Vite + TypeScript
- [ ] Configurar Tailwind CSS
- [ ] Configurar React Router
- [ ] Criar estrutura de pastas
- [ ] Testar: App rodando em localhost

### 1.3 Integração Inicial
- [ ] Configurar CORS no backend
- [ ] Configurar Axios no frontend
- [ ] Testar: Frontend chamando backend

**✅ Checkpoint:** Projetos rodando e se comunicando

---

## FASE 2 - Autenticação
**Complexidade:** ⭐⭐ Simples-Média | **Resultado:** Usuário pode criar conta e logar

### 2.1 Backend - Auth
- [ ] Modelo de Usuário (User) no Prisma
- [ ] Migration inicial
- [ ] Endpoint: POST /auth/register
- [ ] Endpoint: POST /auth/login (retorna JWT)
- [ ] Endpoint: POST /auth/refresh-token
- [ ] Guard de autenticação (JWT)
- [ ] Endpoint: GET /auth/me (dados do usuário logado)

### 2.2 Frontend - Auth
- [ ] Componentes base: Button, Input, Card (com CVA)
- [ ] Tela de Login
- [ ] Tela de Registro
- [ ] Contexto de autenticação (AuthContext)
- [ ] Persistência do token (localStorage)
- [ ] Proteção de rotas (PrivateRoute)
- [ ] Redirecionamento após login

**✅ Checkpoint:** Usuário cria conta, loga e acessa área protegida

---

## FASE 3 - Contas/Carteiras
**Complexidade:** ⭐⭐ Simples-Média | **Resultado:** Usuário pode gerenciar suas contas

### 3.1 Backend - Contas
- [ ] Modelo de Conta (Account) no Prisma
- [ ] Migration
- [ ] Endpoint: GET /accounts (listar)
- [ ] Endpoint: POST /accounts (criar)
- [ ] Endpoint: PUT /accounts/:id (editar)
- [ ] Endpoint: DELETE /accounts/:id (excluir)
- [ ] Campo: saldo inicial
- [ ] Campo: tipo (Corrente, Poupança, Carteira, Dinheiro)
- [ ] Campo: cor e ícone

### 3.2 Frontend - Contas
- [ ] Página de listagem de contas
- [ ] Card de conta com saldo
- [ ] Modal criar conta
- [ ] Modal editar conta
- [ ] Confirmação de exclusão
- [ ] Total de saldo (soma de todas as contas)

**✅ Checkpoint:** Usuário gerencia suas contas com saldo inicial

---

## FASE 4 - Categorias
**Complexidade:** ⭐ Simples | **Resultado:** Usuário pode categorizar transações

### 4.1 Backend - Categorias
- [ ] Modelo de Categoria (Category) no Prisma
- [ ] Migration
- [ ] Seed: categorias padrão (Alimentação, Transporte, Lazer, etc.)
- [ ] Endpoint: GET /categories (listar)
- [ ] Endpoint: POST /categories (criar personalizada)
- [ ] Endpoint: PUT /categories/:id (editar - funciona para padrão e personalizada)
- [ ] Endpoint: DELETE /categories/:id (excluir - padrão e personalizadas)
- [ ] Campo: tipo (Receita ou Despesa)
- [ ] Campo: cor e ícone
- [ ] Campo: isDefault (boolean - indica se é categoria padrão)

### 4.2 Frontend - Categorias
- [ ] Página de listagem de categorias
- [ ] Separação: Receitas vs Despesas
- [ ] Modal criar categoria
- [ ] Modal editar categoria (funciona para padrão e personalizada)
- [ ] Seletor de cor e ícone
- [ ] Indicador de categoria padrão vs personalizada
- [ ] **Componente unificado de seleção de categorias (grid de botões com ícones)**
- [ ] Usar mesmo componente em modal de criar e editar transação

**⚠️ REGRAS IMPORTANTES DE CATEGORIAS:**
- Categorias padrão e personalizadas podem ser editadas e excluídas
- Ambos os tipos funcionam de forma idêntica (mesmas operações disponíveis)
- A interface de seleção de categorias deve ser CONSISTENTE em todos os modais

**✅ Checkpoint:** Categorias prontas para uso nas transações

---

## FASE 5 - Transações (CORE)
**Complexidade:** ⭐⭐⭐ Média | **Resultado:** Sistema financeiro funcional!

### 5.1 Backend - Transações
- [ ] Modelo de Transação (Transaction) no Prisma
- [ ] Migration
- [ ] Endpoint: GET /transactions (listar com filtros)
- [ ] Endpoint: POST /transactions (criar)
- [ ] Endpoint: PUT /transactions/:id (editar)
- [ ] Endpoint: DELETE /transactions/:id (excluir)
- [ ] Campos: valor, descrição, data, tipo (Receita/Despesa)
- [ ] Relacionamentos: conta, categoria
- [ ] **Atualização automática do saldo da conta**
- [ ] Filtros: por conta, categoria, período, tipo

### 5.2 Backend - Transferências
- [ ] Endpoint: POST /transactions/transfer
- [ ] Criar duas transações vinculadas
- [ ] Atualizar saldo de ambas as contas

### 5.3 Frontend - Transações
- [ ] Página de listagem de transações
- [ ] Filtros: período, conta, categoria, tipo
- [ ] Formulário criar transação
- [ ] Seletor de conta
- [ ] Seletor de categoria
- [ ] DatePicker
- [ ] Formulário editar transação
- [ ] Confirmação de exclusão
- [ ] Cores diferenciando receita (verde) e despesa (vermelho)

### 5.4 Frontend - Transferência
- [ ] Modal de transferência entre contas
- [ ] Seletor de conta origem e destino
- [ ] Preview do saldo após transferência

**✅ MVP COMPLETO:** Sistema financeiro funcional - usuário registra transações e acompanha saldo

---
---

# 📊 v1.0 - Dashboard e Visualizações

> **Objetivo:** Usuário tem visão clara de sua situação financeira

---

## FASE 6 - Dashboard
**Complexidade:** ⭐⭐ Simples-Média | **Resultado:** Visão geral das finanças

### 6.1 Backend - Endpoints de Resumo
- [ ] GET /dashboard/summary (saldo total, receitas/despesas do mês)
- [ ] GET /dashboard/by-category (gastos agrupados por categoria)
- [ ] GET /dashboard/monthly-balance (últimos 6 meses)

### 6.2 Frontend - Dashboard
- [ ] Layout do dashboard
- [ ] Card: Saldo total
- [ ] Card: Receitas do mês
- [ ] Card: Despesas do mês
- [ ] Card: Balanço do mês (receita - despesa)
- [ ] Lista: Últimas transações
- [ ] Mini cards: Saldo por conta

**✅ Checkpoint:** Usuário vê resumo financeiro ao abrir o app

---

## FASE 7 - Gráficos
**Complexidade:** ⭐⭐ Simples-Média | **Resultado:** Visualização de dados

### 7.1 Frontend - Gráficos
- [ ] Integrar Recharts
- [ ] Gráfico de pizza: Gastos por categoria (mês atual)
- [ ] Gráfico de barras: Receitas vs Despesas (últimos 6 meses)
- [ ] Gráfico de linha: Evolução do saldo total
- [ ] Tooltips informativos
- [ ] Responsividade dos gráficos

**✅ Checkpoint:** Dados financeiros visualizados graficamente

---

## FASE 8 - Extrato e Filtros Avançados
**Complexidade:** ⭐⭐ Simples-Média | **Resultado:** Navegação detalhada nas transações

### 8.1 Frontend - Extrato
- [ ] Tela de extrato por conta
- [ ] Saldo progressivo por transação
- [ ] Filtros avançados (data, valor, busca por texto)
- [ ] Ordenação (data, valor)
- [ ] Paginação ou scroll infinito

### 8.2 Exportação
- [ ] Exportar extrato em PDF
- [ ] Exportar em CSV/Excel

**✅ Checkpoint:** Usuário consegue analisar histórico detalhado

---

## FASE 9 - Sistema de Orçamento
**Complexidade:** ⭐⭐⭐ Média | **Resultado:** Controle de gastos por categoria

### 9.1 Backend - Orçamento
- [ ] Modelo de Orçamento (Budget) no Prisma
- [ ] Migration
- [ ] Endpoint: GET /budgets (listar orçamentos do mês)
- [ ] Endpoint: POST /budgets (criar/atualizar orçamento)
- [ ] Endpoint: GET /budgets/progress (progresso de cada categoria)
- [ ] Cálculo: gasto atual vs limite

### 9.2 Frontend - Orçamento
- [ ] Tela de configuração de orçamento
- [ ] Definir limite por categoria
- [ ] Barras de progresso (gasto/limite)
- [ ] Cores: verde (<80%), amarelo (80-100%), vermelho (>100%)
- [ ] Sugestão: métodos pré-definidos (50-30-20)

### 9.3 Integração com Dashboard
- [ ] Mostrar alertas de orçamento no dashboard
- [ ] "Você gastou 80% do orçamento de Alimentação"

**✅ v1.0 COMPLETO:** Sistema financeiro completo com dashboard e orçamento

---
---

# 📱 v1.5 - Mobile

> **Objetivo:** Acesso pelo celular com paridade de funcionalidades

---

## FASE 10 - App Mobile
**Complexidade:** ⭐⭐⭐ Média | **Resultado:** App funcionando no celular

### 10.1 Setup Mobile
- [ ] Criar projeto React Native com Expo
- [ ] Configurar Expo Router
- [ ] Configurar NativeWind
- [ ] Configurar chamadas API (reutilizar lógica do web)
- [ ] Configurar SecureStore para tokens

### 10.2 Telas - Auth
- [ ] Tela de Login
- [ ] Tela de Registro
- [ ] Autenticação biométrica (Face ID / Touch ID)

### 10.3 Telas - Core
- [ ] Dashboard (adaptado para mobile)
- [ ] Lista de transações
- [ ] Criar transação (formulário rápido)
- [ ] Lista de contas
- [ ] Lista de categorias

### 10.4 Telas - Orçamento
- [ ] Visualização de orçamento
- [ ] Barras de progresso

### 10.5 Navegação
- [ ] Tab bar inferior (Dashboard, Transações, +Novo, Contas, Mais)
- [ ] Botão flutuante para nova transação

**✅ v1.5 COMPLETO:** App mobile com paridade funcional

---
---

# 🚀 v2.0 - Sistema Avançado

> **Objetivo:** Funcionalidades avançadas para controle financeiro completo

---

## FASE 11 - Transações Recorrentes
**Complexidade:** ⭐⭐⭐ Média | **Resultado:** Automatização de lançamentos repetitivos

### 11.1 Backend - Recorrências
- [ ] Modelo de Transação Recorrente (RecurringTransaction)
- [ ] Regras de repetição:
  - Todo dia X do mês
  - Todo Xº dia útil
  - Último dia do mês
  - Último dia útil
  - A cada X dias/semanas/meses
- [ ] Endpoint: GET /recurring (listar)
- [ ] Endpoint: POST /recurring (criar)
- [ ] Endpoint: PUT /recurring/:id (editar)
- [ ] Endpoint: DELETE /recurring/:id (excluir)

### 11.2 Job de Lançamento Automático
- [ ] Cron job para verificar recorrências diariamente
- [ ] Criar transações automaticamente
- [ ] Marcar como "pendente de confirmação" (opcional)

### 11.3 Frontend - Recorrências
- [ ] Página de listagem de recorrências
- [ ] Formulário criar/editar recorrência
- [ ] Seletor visual de regra de repetição
- [ ] Calendário de fluxo de caixa
- [ ] Projeção de saldo futuro

**✅ Checkpoint:** Salário, aluguel e contas fixas lançados automaticamente

---

## FASE 12 - Sistema de Dívidas
**Complexidade:** ⭐⭐⭐ Média | **Resultado:** Controle de dívidas a pagar e a receber

### 12.1 Backend - Dívidas
- [ ] Modelo de Dívida (Debt)
- [ ] Tipos: A pagar e A receber
- [ ] Campos: pessoa/entidade, valor, vencimento, descrição
- [ ] Dados de pagamento (PIX, código de barras)
- [ ] Status: Pendente, Parcial, Quitada
- [ ] Parcelamento de dívidas
- [ ] Endpoints CRUD

### 12.2 Vinculação Dívida-Transação
- [ ] Ao pagar dívida, criar transação automaticamente
- [ ] Vincular transação existente a dívida
- [ ] Atualizar saldo devedor

### 12.3 Frontend - Dívidas
- [ ] Dashboard de dívidas (a pagar vs a receber)
- [ ] Formulário criar/editar dívida
- [ ] Tela de detalhes com histórico de pagamentos
- [ ] Botão "Copiar PIX"
- [ ] Alertas de vencimento próximo

**✅ Checkpoint:** Usuário controla o que deve e o que tem a receber

---

## FASE 13 - Cartões de Crédito
**Complexidade:** ⭐⭐⭐⭐ Média-Alta | **Resultado:** Gestão completa de cartões

### 13.1 Backend - Cartões
- [ ] Modelo de Cartão de Crédito (CreditCard)
- [ ] Campos: nome, limite, data fechamento, data vencimento
- [ ] Cálculo de limite disponível
- [ ] Modelo de Fatura (Invoice)
- [ ] Status da fatura: aberta, fechada, paga

### 13.2 Parcelamentos
- [ ] Modelo de Parcelamento (Installment)
- [ ] Campos: descrição, valor total, número de parcelas
- [ ] Parcela atual (ex: 5/12)
- [ ] Impacto nas faturas futuras

### 13.3 Gastos Recorrentes no Cartão
- [ ] Assinaturas (Netflix, Spotify, etc.)
- [ ] Separação: pontuais vs recorrentes vs parcelamentos

### 13.4 Frontend - Cartões
- [ ] Listagem de cartões com limite disponível
- [ ] Visualização da fatura atual
- [ ] Separação por tipo de gasto
- [ ] Histórico de faturas
- [ ] Previsão de fatura futura

**✅ Checkpoint:** Controle completo de cartões e faturas

---

## FASE 14 - Sistema de Envelopes (Metas e Fundos)
**Complexidade:** ⭐⭐⭐ Média | **Resultado:** Separação real de dinheiro em potes/cofres para objetivos específicos

### 14.1 Backend - Envelopes
- [ ] Modelo de Envelope (Envelope)
- [ ] Modelo de Transação de Envelope (EnvelopeTransaction)
- [ ] Tipos: FUNDO (reservas) e META (objetivos de compra)
- [ ] Status: ATIVO, COMPLETO, PAUSADO, ARQUIVADO
- [ ] Campos principais: nome, ícone, cor, meta_valor, saldo_atual, tipo, conta_id
- [ ] Campos para META: produto (nome, url, imagem, preço)
- [ ] Depósito automático: valor fixo ou percentual, frequência configurável
- [ ] Endpoints CRUD completos
- [ ] Endpoint: POST /envelopes/:id/deposit (depositar no envelope)
- [ ] Endpoint: POST /envelopes/:id/withdraw (retirar do envelope)
- [ ] Endpoint: GET /envelopes/:id/transactions (histórico)

### 14.2 Lógica de Transferência Conta ↔ Envelope
- [ ] Depositar: cria Transaction de SAÍDA na conta + EnvelopeTransaction de DEPOSITO
- [ ] Retirar: cria EnvelopeTransaction de RETIRADA + Transaction de ENTRADA na conta
- [ ] Envelope tem saldo próprio separado da conta
- [ ] Validação: não permitir depositar mais que saldo da conta
- [ ] Validação: não permitir retirar mais que saldo do envelope

### 14.3 Depósito Automático Recorrente
- [ ] Job/Cron para depósitos automáticos
- [ ] Suporte a valor fixo (ex: R$ 200/mês)
- [ ] Suporte a percentual de receitas (ex: 10% do salário)
- [ ] Frequências: DIARIA, SEMANAL, QUINZENAL, MENSAL
- [ ] Configurar dia específico para depósito

### 14.4 Sistema de Rendimento Automático
- [ ] Integração com API do Banco Central para buscar CDI diário
- [ ] Job/Cron diário para atualizar valor do CDI
- [ ] Armazenar histórico do CDI para cálculos retroativos
- [ ] Calcular rendimento diário baseado no CDI configurado
- [ ] Aplicar rendimento automaticamente aos envelopes
- [ ] Criar transação de rendimento no histórico
- [ ] Suporte para diferentes tipos de rendimento (CDI, Poupança, Taxa Fixa)

**API sugerida:** https://api.bcb.gov.br/dados/serie/bcdata.sgs.12/dados/ultimos/1?formato=json (CDI oficial do Banco Central)

### 14.5 Projeções Inteligentes
- [ ] Calcular ritmo de economia baseado em histórico
- [ ] Projetar tempo para atingir meta
- [ ] Sugestão de valor mensal para cumprir prazo
- [ ] Cálculo automático de progresso (%)

### 14.6 Funcionalidades para tipo META
- [ ] Rastreamento de preço do produto
- [ ] Alertas de variação de preço (subiu/caiu)
- [ ] Status COMPLETO quando saldo_atual >= meta_valor
- [ ] Botão "REALIZAR META" quando completar
- [ ] Gamificação: notificações em 25%, 50%, 75%, 100%

### 14.7 Funcionalidades para tipo FUNDO
- [ ] Sem finalização automática (continua acumulando)
- [ ] Histórico de depósitos e retiradas
- [ ] Alertas quando saldo ficar abaixo da meta

### 14.8 Frontend - Envelopes
- [ ] Dashboard de envelopes (lista com cards visuais)
- [ ] Exibir saldo de cada envelope separadamente
- [ ] Exibir total em envelopes vs total nas contas
- [ ] Formulário criar envelope (escolher tipo: FUNDO ou META)
- [ ] Formulário editar envelope
- [ ] Modal depositar no envelope (transferir da conta)
- [ ] Modal retirar do envelope (devolver para conta)
- [ ] Transferir entre envelopes
- [ ] Barras de progresso visual
- [ ] Histórico de movimentações do envelope
- [ ] Cores: verde (<80%), amarelo (80-99%), verde-escuro (100%+)

### 14.9 Frontend - Específico para META
- [ ] Exibir imagem do produto
- [ ] Link para produto (botão "Ver Produto")
- [ ] Indicador de preço atual vs inicial
- [ ] Badge de alerta de preço
- [ ] Botão "COMPRAR/REALIZAR" quando completo
- [ ] Projeção visual: "Falta X meses"
- [ ] Sugestão: "Guardar R$ X/mês para atingir no prazo"

### 14.10 Frontend - Específico para FUNDO
- [ ] Ícones específicos (emergência, IPVA, IPTU, férias)
- [ ] Indicação de prazo/vencimento (ex: IPVA vence em Março)
- [ ] Histórico de uso do fundo

### 14.11 Integração com Dashboard Principal
- [ ] Card "Envelopes" no dashboard
- [ ] Total guardado em envelopes
- [ ] Resumo: Saldo em Contas vs Saldo em Envelopes
- [ ] Alertas de metas próximas de completar

**✅ Checkpoint:** Usuário separa dinheiro fisicamente em envelopes para objetivos (fundos e metas)

---

## FASE 15 - Sistema de Notificações
**Complexidade:** ⭐⭐⭐ Média | **Resultado:** Alertas proativos

### 15.1 Backend - Notificações
- [ ] Modelo de Notificação (Notification)
- [ ] Tipos: orçamento, dívida, recorrência, meta
- [ ] Status: lida, não lida
- [ ] Configurações do usuário

### 15.2 Push Notifications (Mobile)
- [ ] Configurar Firebase (FCM) + expo-notifications
- [ ] Registrar device token
- [ ] Enviar push para alertas de orçamento
- [ ] Enviar push para vencimento de dívidas
- [ ] Enviar push para recorrências

### 15.3 Frontend - Central de Notificações
- [ ] Lista de notificações
- [ ] Marcar como lida
- [ ] Configurações de preferências

**✅ v2.0 COMPLETO:** Sistema financeiro avançado com recorrências, dívidas, cartões, metas e notificações

---
---

# 🤖 v3.0 - Sistema Inteligente

> **Objetivo:** Automação e inteligência para facilitar a vida do usuário

---

## FASE 16 - Captura Automática de Notificações (Android)
**Complexidade:** ⭐⭐⭐⭐ Alta | **Resultado:** Transações criadas automaticamente

### 16.1 Listener de Notificações
- [ ] Implementar NotificationListenerService (Android only)
- [ ] Solicitar permissões necessárias
- [ ] Interceptar notificações de apps bancários

### 16.2 Parser Inteligente
- [ ] Extrair valor, estabelecimento, data/hora
- [ ] Suporte para múltiplos bancos (Nubank, Inter, Itaú, etc.)
- [ ] Identificar conta automaticamente

### 16.3 Criação Automática de Transação
- [ ] Criar transação como "pendente de categorização"
- [ ] Notificar usuário para categorizar
- [ ] Fila de transações pendentes

### 16.4 UI de Transações Pendentes
- [ ] Badge de pendências no menu
- [ ] Lista para categorizar rapidamente
- [ ] Categorização em 1 clique

**✅ Checkpoint:** Gastos registrados automaticamente

---

## FASE 17 - Auto-Categorização (ML)
**Complexidade:** ⭐⭐⭐⭐⭐ Muito Alta | **Resultado:** Categorias sugeridas automaticamente

### 17.1 Coleta de Dados
- [ ] Armazenar padrões de categorização do usuário
- [ ] Dados: nome do estabelecimento, valor, horário, categoria escolhida

### 17.2 Modelo de Sugestão
- [ ] Algoritmo simples baseado em frequência
- [ ] Sugerir categoria mais provável
- [ ] Indicador de confiança

### 17.3 Níveis de Automação
- [ ] Apenas sugestão (usuário confirma)
- [ ] Auto-preencher (usuário pode mudar)
- [ ] Totalmente automático (alta confiança)

**✅ Checkpoint:** Sistema aprende preferências do usuário

---

## FASE 18 - Scanner de Notas Fiscais (OCR)
**Complexidade:** ⭐⭐⭐⭐⭐ Muito Alta | **Resultado:** Transações via foto

### 18.1 Captura de Imagem
- [ ] Tirar foto da nota fiscal
- [ ] Recorte e ajuste automático

### 18.2 Extração de Dados (OCR)
- [ ] Integrar serviço de OCR (Google Vision ou similar)
- [ ] Extrair itens e valores
- [ ] Identificar estabelecimento e data

### 18.3 Criar Transações
- [ ] Criar transação a partir dos dados extraídos
- [ ] Armazenar imagem anexada
- [ ] Permitir correção manual

**✅ Checkpoint:** Transações criadas fotografando recibos

---

## FASE 19 - Relatórios Avançados
**Complexidade:** ⭐⭐⭐⭐ Alta | **Resultado:** Análises profundas

### 19.1 Comparação Ano a Ano
- [ ] Gastos por categoria: este ano vs ano passado
- [ ] Evolução mensal comparativa

### 19.2 Análise de Tendências
- [ ] Gráfico de evolução por categoria
- [ ] Identificar vazamentos financeiros
- [ ] Padrões de gastos (dia da semana, horário)

### 19.3 Relatórios Customizáveis
- [ ] Filtros avançados
- [ ] Exportar em PDF/Excel

**✅ Checkpoint:** Insights profundos sobre finanças

---

## FASE 20 - Funcionalidades Extras
**Complexidade:** ⭐⭐⭐⭐ Alta | **Resultado:** Features de power user

### 20.1 Sistema de Eventos (Viagens, Festas)
- [ ] Criar evento com orçamento
- [ ] Vincular gastos ao evento
- [ ] Rateio entre participantes

### 20.2 Importação de Extratos
- [ ] Suporte a OFX e CSV
- [ ] Mapeamento de colunas
- [ ] Evitar duplicatas

### 20.3 Simulador de Cenários
- [ ] "E se eu cancelar Netflix?"
- [ ] Comparação lado a lado

### 20.4 Widgets Mobile
- [ ] Widget de saldo na tela inicial
- [ ] Widget de gastos do mês

**✅ v3.0 COMPLETO:** Sistema financeiro inteligente e automatizado

---
---

# 🚢 Deploy e Publicação

## FASE 21 - Infraestrutura de Produção
**Complexidade:** ⭐⭐⭐ Média | **Resultado:** Sistema online

### 21.1 Backend
- [ ] Deploy no Railway
- [ ] Configurar variáveis de ambiente
- [ ] Configurar PostgreSQL no Neon
- [ ] CI/CD com GitHub Actions

### 21.2 Frontend Web
- [ ] Deploy na Vercel
- [ ] Configurar domínio
- [ ] SSL/HTTPS automático

### 21.3 Mobile
- [ ] Preparar assets (ícones, splash screen)
- [ ] Configurar EAS Build
- [ ] Publicar na Google Play Store
- [ ] Publicar na Apple App Store

**✅ SISTEMA PUBLICADO:** Disponível para usuários reais

---

## Resumo por Versão

| Versão | Fases | O que entrega |
|--------|-------|---------------|
| **MVP** | 1-5 | Sistema financeiro básico funcional |
| **v1.0** | 6-9 | Dashboard, gráficos, orçamento |
| **v1.5** | 10 | App mobile |
| **v2.0** | 11-15 | Recorrências, dívidas, cartões, metas, notificações |
| **v3.0** | 16-20 | Captura automática, ML, OCR, relatórios avançados |
| **Deploy** | 21 | Sistema em produção |

---

## Próximos Passos

1. Começar pela **Fase 1** - Setup do projeto
2. Completar **MVP** (Fases 1-5) antes de qualquer coisa
3. Testar MVP com usuários reais
4. Avançar para v1.0 baseado em feedback
5. Cada fase deve estar funcional antes de avançar

---

*Documento criado em: Janeiro/2026*
*Última atualização: Janeiro/2026*

---

## Notas para Manutenção da Documentação

> **IMPORTANTE:** Este documento deve ser atualizado sempre que novas regras de negócio ou decisões técnicas forem definidas durante o desenvolvimento.
>
> Ao definir uma nova funcionalidade ou regra:
> - Adicionar nas tarefas da fase correspondente
> - Incluir regras importantes em destaque (⚠️)
> - Atualizar data de última atualização
>
> Manter sincronizado com: SSR.md e PLANEJAMENTO.md
