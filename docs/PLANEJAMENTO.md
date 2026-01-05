# Tony Save Your Finances - Planejamento do Projeto

## Visão Geral
Sistema de controle financeiro pessoal com site web e aplicativo mobile, incluindo notificações push para registro automático de transações.

---

## Objetivos Principais
- Controlar receitas e despesas pessoais
- Visualizar gastos e ganhos de forma clara
- **Capturar automaticamente notificações bancárias** e criar entradas genéricas
- Permitir categorização e edição posterior das transações capturadas
- Sincronização automática entre web e mobile

---

## Plataformas

### 1. Site Web
**Funcionalidades Principais:**
- Dashboard com visão geral financeira
- Cadastro de receitas e despesas
- Categorização de transações
- **Indicadores visuais chamativos para transações pendentes:**
  - Badge/contador com número de pendências
  - Banner/alerta no topo da página
  - Animações/pulsos para chamar atenção
  - Seção dedicada com destaque visual
- Relatórios e gráficos
- Gestão de contas bancárias/carteiras
- Histórico de transações

### 2. Aplicativo Mobile
**Princípio: Paridade total com a versão Web** - O usuário deve conseguir fazer tudo que faz no site também pelo app.

**Funcionalidades Principais:**
- **Todas as funcionalidades do site web disponíveis no mobile**
- Visualização rápida do saldo
- Registro rápido de transações
- **Notificações Push** para lembrar de registrar gastos
- Auto-entrada via notificação (registro automático no banco)
- Sincronização em tempo real

**Funcionalidades Exclusivas do Mobile:**
- Captura automática de notificações bancárias
- Scanner de notas fiscais com câmera (OCR)
- Widgets para tela inicial
- Modo oculto com gesto (shake)
- Autenticação biométrica (Face ID / Touch ID)

---

## Funcionalidades Detalhadas

### Gestão de Transações
- [ ] Cadastro de receitas
- [ ] Cadastro de despesas
- [ ] Edição e exclusão de transações
- [ ] Categorias personalizáveis (Alimentação, Transporte, Lazer, etc.)
- [ ] **Gestão completa de categorias:**
  - [ ] Categorias padrão vêm pré-configuradas mas podem ser editadas e excluídas
  - [ ] Categorias personalizadas funcionam igual às padrão
  - [ ] Tela dedicada para gerenciar categorias (criar, editar, excluir)
  - [ ] Todas as categorias podem ser editadas e excluídas (padrão e personalizadas)
  - [ ] Interface de seleção de categorias consistente em toda aplicação (grid de botões com ícones)
- [ ] Tags/etiquetas para organização
- [ ] Anexar comprovantes/notas fiscais
- [ ] **Auto-categorização por Machine Learning:**
  - [ ] Aprender com categorizações manuais do usuário
  - [ ] **Dados utilizados para aprendizado:**
    - [ ] Nome do estabelecimento (padrão mais forte)
    - [ ] Valor da transação
    - [ ] Horário da compra
    - [ ] Dia da semana
    - [ ] Frequência/recorrência
    - [ ] Método de pagamento
  - [ ] **Níveis de automação configuráveis:**
    - [ ] Sugestão (mostra categoria, usuário confirma)
    - [ ] Auto-preencher (preenche, usuário pode editar)
    - [ ] Totalmente automático (alta confiança, sem intervenção)
  - [ ] Indicador de confiança da sugestão (ex: 95%)
  - [ ] Correção do usuário retroalimenta o modelo
  - [ ] Mapeamento de estabelecimentos similares (ex: "Burger King" ≈ "McDonald's")
  - [ ] Tratamento especial para casos ambíguos (Mercado, Amazon, PIX)
  - [ ] Métricas de acurácia e tempo economizado
  - [ ] Sugestão de subcategoria (ex: Alimentação → Delivery)

### Sistema de Transações Recorrentes (Receitas e Despesas Fixas)
- [ ] **Cadastrar receitas recorrentes:**
  - [ ] Salário mensal
  - [ ] Freelance fixo
  - [ ] Aluguéis recebidos
  - [ ] Pensões/benefícios
  - [ ] Dividendos/investimentos
- [ ] **Cadastrar despesas recorrentes:**
  - [ ] Aluguel
  - [ ] Condomínio
  - [ ] Contas (água, luz, internet, telefone)
  - [ ] Seguros
  - [ ] Mensalidades (escola, cursos)
  - [ ] Planos de saúde
- [ ] **Regras de repetição flexíveis:**
  - [ ] Todo dia X do mês (ex: dia 22)
  - [ ] Todo Xº dia útil do mês (ex: 5º dia útil)
  - [ ] Toda Xª semana do mês (ex: 1ª segunda-feira)
  - [ ] Último dia do mês
  - [ ] Último dia útil do mês
  - [ ] A cada X dias/semanas/meses
- [ ] **Sistema detecta padrões automaticamente:**
  - [ ] Analisa transações passadas
  - [ ] Sugere criar recorrência se detectar repetição
  - [ ] "Detectamos que você recebe R$ 3.000 todo dia 5. Marcar como salário recorrente?"
- [ ] **Lançamento automático:**
  - [ ] Cria transação automaticamente na data prevista
  - [ ] Opção de confirmação antes de lançar
  - [ ] Ajuste de valor se necessário
- [ ] **Previsão de fluxo de caixa:**
  - [ ] Calendário com receitas/despesas futuras
  - [ ] Projeção de saldo nos próximos meses
  - [ ] Alertas de meses apertados
- [ ] Gestão de recorrências (editar, pausar, cancelar)
- [ ] Histórico de lançamentos da recorrência

### Dashboard e Relatórios
- [ ] Saldo atual
- [ ] Resumo mensal (receitas vs despesas)
- [ ] Gráficos de gastos por categoria
- [ ] Comparação entre períodos
- [ ] Metas de economia
- [ ] Projeções financeiras

### Sistema de Orçamento Inteligente
- [ ] **Sugestão automática de divisão baseada em incomings (receitas totais)** entre categorias
- [ ] Suporte para múltiplas fontes de renda:
  - [ ] Salário fixo
  - [ ] Freelance/bicos
  - [ ] Vendas
  - [ ] Investimentos/dividendos
  - [ ] Outras entradas variáveis
- [ ] Cálculo automático de orçamento baseado em receita total do mês
- [ ] Métodos de orçamento pré-configurados:
  - [ ] Regra 50-30-20 (50% essenciais, 30% desejos, 20% poupança)
  - [ ] Regra 70-20-10 (70% gastos, 20% poupança, 10% investimentos)
  - [ ] Método Kakebo (japonês)
  - [ ] Orçamento Base Zero
- [ ] **Análise de padrões de gasto históricos**
- [ ] Ajuste automático de percentuais baseado no comportamento real
- [ ] Sugestões personalizadas: "Você gasta 35% em alimentação, considere ajustar"
- [ ] Alertas quando ultrapassar limite de categoria
- [ ] Comparação: Orçamento planejado vs Gasto real
- [ ] Recomendação de quanto guardar baseado em receitas e despesas fixas

### Sistema de Captura Automática de Notificações
- [ ] **Listener de notificações bancárias** (interceptar notificações de bancos/cartões)
- [ ] Parser inteligente para extrair dados (valor, estabelecimento, data/hora)
- [ ] Criação automática de transação genérica (pendente de categorização)
- [ ] Fila de transações para revisão e categorização
- [ ] Confirmação/edição rápida pelo usuário
- [ ] Suporte para múltiplos bancos (Nubank, Inter, Itaú, etc.)
- [ ] Machine Learning para melhorar extração de dados ao longo do tempo

### Sistema de Notificações Internas
- [ ] Lembretes para categorizar transações pendentes
- [ ] Notificação de vencimento de contas/dívidas
- [ ] **Push notifications para alertas de orçamento:**
  - [ ] Quando atingir 80% do limite de uma categoria
  - [ ] Quando estourar limite de uma categoria específica
  - [ ] Quando estourar orçamento geral do mês
  - [ ] Quando estiver gastando muito rápido ("no ritmo atual, vai estourar")
  - [ ] Alertas de fim de mês ("Faltam 3 dias, você tem R$ X disponível")
- [ ] Sugestões inteligentes baseadas em padrões de gasto
- [ ] Notificações configuráveis (usuário escolhe quais quer receber)

### Gestão de Dívidas e Empréstimos
- [ ] Registro de dívidas a pagar (você deve)
- [ ] Registro de empréstimos a receber (devem a você)
- [ ] **Atribuir a pessoa física** (João, Maria, etc.) **ou entidade** (loja, empresa, serviço)
- [ ] Cadastro de credores/devedores recorrentes
- [ ] **Armazenar dados de pagamento:**
  - [ ] Chave PIX (CPF, celular, e-mail, aleatória)
  - [ ] Dados bancários (banco, agência, conta)
  - [ ] Código de barras (boleto)
  - [ ] QR Code PIX
- [ ] Ação rápida "Copiar PIX" direto da dívida
- [ ] Definir deadline/prazo de pagamento
- [ ] Status da dívida (pendente, paga parcialmente, quitada)
- [ ] Parcelamento de dívidas
- [ ] Notificações de vencimento próximo
- [ ] **Vincular transações aos pagamentos:**
  - [ ] Ao pagar dívida, criar transação automaticamente
  - [ ] Vincular transação existente a uma dívida
  - [ ] Atualizar saldo da conta e status da dívida
  - [ ] Histórico mostra transação vinculada
- [ ] Histórico de pagamentos parciais
- [ ] Anexar comprovantes/conversas/notas fiscais
- [ ] Calcular juros/multas (opcional)
- [ ] Integração com contatos do telefone

### Contas e Carteiras (Saldo Disponível)
- [ ] **Cadastrar múltiplas contas:**
  - [ ] Conta corrente (Nubank, Inter, Itaú, etc.)
  - [ ] Poupança
  - [ ] Carteiras digitais (PicPay, Mercado Pago, PayPal)
  - [ ] Dinheiro físico
  - [ ] Outras contas
- [ ] **Saldo inicial ao criar conta** (quanto você tem nela no momento do cadastro)
- [ ] **Saldo calculado automaticamente** baseado nas transações:
  - Entrada (receita) → aumenta saldo
  - Saída (despesa) → diminui saldo
  - Transferência entre contas → atualiza ambas
- [ ] **Cada transação é vinculada a uma conta específica**
- [ ] Sistema mantém "foto" atualizada do saldo real de cada conta
- [ ] Transferências entre contas
- [ ] Histórico completo por conta
- [ ] Conciliação bancária (comparar saldo real vs saldo no app)

### Sistema de Cartões de Crédito
- [ ] **Cadastrar múltiplos cartões de crédito**
- [ ] Atribuir gastos a cartões específicos
- [ ] **Visualizar fatura atual por cartão:**
  - [ ] Gastos ativos/pontuais do mês
  - [ ] Gastos recorrentes/fixos (assinaturas, mensalidades)
  - [ ] Parcelamentos (compras em andamento)
  - [ ] Total da fatura
- [ ] **Separação clara entre tipos de gasto:**
  - [ ] Gastos pontuais (compras normais do mês)
  - [ ] Gastos recorrentes (Netflix, Spotify, academia)
  - [ ] Parcelamentos (geladeira 5/12, notebook 3/10)
- [ ] **Previsão de fatura futura:**
  - [ ] Baseada em gastos recorrentes confirmados
  - [ ] Baseada em média de gastos variáveis
  - [ ] Baseada em parcelamentos cadastrados (parcelas restantes)
  - [ ] Projeção para próximos meses
- [ ] **Cadastro de parcelamentos:**
  - [ ] Nome da compra
  - [ ] Valor total e valor da parcela
  - [ ] Número de parcelas (ex: 12x)
  - [ ] Parcela atual (ex: 5/12)
  - [ ] Data da primeira parcela
  - [ ] Cartão vinculado
  - [ ] Categoria da compra
  - [ ] Visualizar parcelas restantes no calendário
  - [ ] Alerta quando parcelamento está acabando
- [ ] Limite do cartão e disponível
- [ ] Data de fechamento e vencimento
- [ ] Alertas de proximidade do limite
- [ ] Histórico de faturas pagas
- [ ] Status da fatura (aberta, fechada, paga, atrasada)
- [ ] **Sistema de Cashback e Benefícios:**
  - [ ] Configurar regras de cashback por cartão
  - [ ] Cashback padrão (ex: 1% em tudo)
  - [ ] Cashback por categoria (ex: 5% em restaurantes)
  - [ ] Programa de pontos/milhas (ex: 1 ponto por R$ 1)
  - [ ] Cálculo automático de benefícios em cada transação
  - [ ] Permitir ajuste manual na transação (promoções especiais)
  - [ ] Relatório mensal de cashback acumulado
  - [ ] Relatório de pontos/milhas acumulados
  - [ ] Histórico de benefícios recebidos
  - [ ] Rastreamento separado (não afeta saldo da conta)

### Sistema Unificado de Envelopes (Metas e Fundos)

> **Decisão de Design (Janeiro/2026):** Sistema unificado que combina "Metas de Economia" e "Reservas/Envelopes" em um único conceito.
> Envelopes são "potes separados" com saldo próprio (não virtual), vinculados a uma conta específica.

**Conceito:** Envelope funciona como "cofre separado" - depositar no envelope retira da conta, retirar do envelope devolve para conta.

- [ ] **Tipos de Envelope:**
  - [ ] **FUNDO**: Reservas contínuas (IPVA, IPTU, emergência, férias)
    - Nunca finaliza automaticamente
    - Continua acumulando após atingir meta
    - Alertas quando saldo cai abaixo da meta
  - [ ] **META**: Objetivos específicos de compra (notebook, viagem, carro)
    - Status muda para COMPLETO ao atingir 100%
    - Pode vincular produto (nome, URL, imagem, preço)
    - Gamificação (notificações em 25%, 50%, 75%, 100%)
- [ ] **Operações:**
  - [ ] Depositar no envelope (retira da conta)
  - [ ] Retirar do envelope (devolve para conta)
  - [ ] Transferir entre envelopes
  - [ ] Histórico de movimentações
- [ ] **Depósito Automático Recorrente:**
  - [ ] Valor fixo (ex: R$ 200/mês)
  - [ ] Percentual de receitas (ex: 10% do salário)
  - [ ] Frequências: diária, semanal, quinzenal, mensal
  - [ ] Configurar dia específico
  - [ ] Pausar/retomar
- [ ] **Projeções e Inteligência:**
  - [ ] Calcular tempo para atingir meta baseado em histórico
  - [ ] Sugerir valor mensal para cumprir prazo
  - [ ] Progresso visual (%)
- [ ] **Específico para META:**
  - [ ] Vincular produto (imagem, URL, preço)
  - [ ] Rastreamento de preço
  - [ ] Alertas de variação
  - [ ] Botão "REALIZAR META" quando completar
- [ ] **Específico para FUNDO:**
  - [ ] Indicação de vencimento (ex: IPVA vence em Março)
  - [ ] Histórico de uso

### Sistema de Garantias de Produtos
- [ ] **Registrar garantia de produtos comprados:**
  - [ ] Nome do produto
  - [ ] Data da compra
  - [ ] Prazo de garantia (meses/anos)
  - [ ] Loja/fornecedor
  - [ ] Número da nota fiscal
  - [ ] Vincular à transação de compra
- [ ] Armazenar documentos:
  - [ ] Foto/PDF da nota fiscal
  - [ ] Foto do produto
  - [ ] Certificado de garantia
  - [ ] Manual do produto
- [ ] **Alertas de vencimento:**
  - [ ] Notificar 30 dias antes do fim da garantia
  - [ ] "Sua geladeira sai da garantia em 1 mês"
- [ ] Status da garantia (ativa, vencida, acionada)
- [ ] Histórico de acionamento de garantia
- [ ] Dados de contato para acionar (telefone, site)
- [ ] Filtros: garantias ativas, vencendo em breve, vencidas

### Relatórios e Análises Avançadas
- [ ] **Comparação Ano a Ano:**
  - [ ] Quanto gastou em cada categoria este ano vs ano passado
  - [ ] Evolução de gastos mensais (2024 vs 2025)
  - [ ] Identificar onde houve maior aumento/redução
- [ ] **Análise de Tendências:**
  - [ ] Seus gastos estão aumentando ou diminuindo?
  - [ ] Gráfico de evolução por categoria
  - [ ] Previsão baseada em tendência
- [ ] **Identificar "Vazamentos Financeiros":**
  - [ ] Pequenos gastos que somam muito (cafézinho, Uber, iFood)
  - [ ] "Você gastou R$ 450 em pequenos lanches este mês"
  - [ ] Top 10 gastos recorrentes pequenos
- [ ] **Análise de Hábitos:**
  - [ ] Qual dia da semana você gasta mais?
  - [ ] Qual horário do dia gasta mais?
  - [ ] Padrões sazonais (gasta mais em dezembro?)
  - [ ] Correlações (gasta mais quando recebe salário?)
- [ ] Relatórios customizáveis
- [ ] Exportar relatórios em PDF/Excel
- [ ] Gráficos interativos

### Alertas Inteligentes Personalizados
- [ ] **Alertas baseados em padrões:**
  - [ ] "Você normalmente gasta R$ 400 em transporte, já gastou R$ 350 e faltam 15 dias"
  - [ ] "Mês passado economizou R$ 800, este mês só R$ 200. O que mudou?"
  - [ ] "Você está gastando 40% a mais que a média dos últimos 3 meses"
- [ ] **Sugestões de economia:**
  - [ ] "Cancele 2 assinaturas e economize R$ 60/mês"
  - [ ] "Você pode trocar de plano e economizar R$ 30"
- [ ] **Alertas de oportunidade:**
  - [ ] "Você atingiu meta de poupança, pode realizar sonho X"
- [ ] Personalização de sensibilidade dos alertas
- [ ] Escolher quais alertas receber

### Importação e Exportação de Dados
- [ ] **Importar extratos bancários:**
  - [ ] Suporte a OFX (Open Financial Exchange)
  - [ ] Suporte a CSV
  - [ ] Mapeamento inteligente de colunas
  - [ ] Importar histórico de 6-12 meses
  - [ ] Evitar duplicatas
- [ ] **Exportação completa:**
  - [ ] Exportar todos os dados em JSON
  - [ ] Exportar relatórios em Excel/CSV
  - [ ] Exportar extratos em PDF
- [ ] **Backup automático:**
  - [ ] Backup diário na nuvem (criptografado)
  - [ ] Restaurar dados de backup
  - [ ] Histórico de backups
- [ ] Migração de outros apps de finanças

### Dashboard Customizável
- [ ] **Widgets disponíveis:**
  - [ ] Saldo atual
  - [ ] Resumo mensal
  - [ ] Gráfico de gastos
  - [ ] Próximas contas a pagar
  - [ ] Metas em andamento
  - [ ] Cashback do mês
  - [ ] Transações recentes
  - [ ] Alertas importantes
- [ ] Arrastar e soltar widgets
- [ ] Redimensionar widgets
- [ ] Salvar layouts personalizados
- [ ] Modo "Visão Executiva" (só números principais)
- [ ] Modo "Visão Detalhada" (tudo expandido)
- [ ] Temas/cores personalizáveis


### Sistema de Eventos (Viagens, Festas, Projetos)
- [ ] **Cadastrar evento (opcional, pode criar antes ou na hora):**
  - [ ] Tipos: Viagem, Casamento, Festa, Reforma, Projeto, Personalizado
  - [ ] Nome e descrição do evento
  - [ ] Data de início e fim (opcional)
  - [ ] Orçamento total planejado (opcional)
  - [ ] Categorias específicas do evento
- [ ] **Modo Evento (ativar/desativar):**
  - [ ] Botão rápido para entrar no "Modo Evento"
  - [ ] Indicador visual de que está no modo evento (badge, cor, ícone)
  - [ ] Todos os gastos registrados ficam marcados como "evento"
  - [ ] Opção de confirmar antes de vincular cada gasto
  - [ ] Sair do modo evento com um toque
  - [ ] Ao sair/finalizar, perguntar a qual evento associar os gastos
  - [ ] Pode associar a evento existente ou criar novo nesse momento
  - [ ] Lembrete se ficar muito tempo no modo evento
- [ ] **Orçamento separado do dia a dia:**
  - [ ] Gastos do evento não misturam com gastos normais
  - [ ] Controle independente de limite
  - [ ] Visualização isolada
  - [ ] Relatórios do mês podem incluir ou excluir eventos
- [ ] **Funcionalidades para Viagens:**
  - [ ] Conversor de moeda em tempo real
  - [ ] Gastos em moeda estrangeira
  - [ ] Conversão automática para BRL no relatório
  - [ ] Múltiplas moedas no mesmo evento
- [ ] **Rateio com participantes:**
  - [ ] Adicionar participantes (amigos/família)
  - [ ] Registrar quem pagou cada despesa
  - [ ] Calcular quanto cada um deve
  - [ ] Gerar resumo de "quem deve pra quem"
  - [ ] Marcar quando foi acertado
- [ ] **Relatório final do evento:**
  - [ ] Total gasto
  - [ ] Gasto por categoria
  - [ ] Gasto por participante
  - [ ] Comparação: planejado vs realizado
  - [ ] Exportar relatório em PDF
- [ ] Timeline do evento (gastos ao longo dos dias)
- [ ] Anexar fotos e documentos
- [ ] Status: Planejando, Em andamento, Finalizado
- [ ] Arquivar eventos antigos

### Sistema de Lembretes Financeiros
- [ ] **Tipos de lembrete:**
  - [ ] Pagar conta/dívida
  - [ ] Cancelar serviço/trial
  - [ ] Verificar fatura do cartão
  - [ ] Categorizar transações pendentes
  - [ ] Revisar orçamento mensal
  - [ ] Verificar garantias vencendo
  - [ ] Lembrete personalizado
- [ ] **Configurar lembrete:**
  - [ ] Data e hora específica
  - [ ] Dias antes de um vencimento
  - [ ] Recorrente (todo mês, semana, etc.)
  - [ ] Prioridade (baixa, média, alta)
  - [ ] Anexar valor/documento
- [ ] **Lembretes automáticos:**
  - [ ] 3 dias antes de vencimento de conta
  - [ ] Dia do vencimento
  - [ ] 1 dia antes do fim do trial
  - [ ] Quando tiver transações não categorizadas há +3 dias
  - [ ] Final do mês (revisar orçamento)
- [ ] **Ações rápidas no lembrete:**
  - [ ] Marcar como concluído
  - [ ] Adiar para depois
  - [ ] Ir direto para a tarefa (pagar conta, categorizar, etc.)
  - [ ] Criar transação/pagamento
- [ ] Notificação push
- [ ] Integração com calendário do celular
- [ ] Histórico de lembretes concluídos
- [ ] Snooze (adiar por X minutos/horas/dias)

### Scanner de Notas Fiscais (OCR)
- [ ] **Escanear nota fiscal com câmera:**
  - [ ] Tirar foto da nota fiscal
  - [ ] OCR extrai texto automaticamente
  - [ ] Identifica produtos, valores, data, loja
  - [ ] Suporte para diferentes formatos de nota
- [ ] **Processar cupom fiscal:**
  - [ ] Detectar itens automaticamente
  - [ ] Extrair valor de cada produto
  - [ ] Identificar categoria do produto (alimentos, limpeza, etc.)
  - [ ] Total da nota
- [ ] **Criar transações detalhadas:**
  - [ ] Opção 1: Uma transação com todos os itens
  - [ ] Opção 2: Múltiplas transações (1 por item)
  - [ ] Categorização automática por produto
  - [ ] Vincula à conta selecionada
- [ ] **Revisar e editar:**
  - [ ] Confirmar itens extraídos
  - [ ] Corrigir erros de leitura
  - [ ] Adicionar/remover produtos
  - [ ] Ajustar categorias
- [ ] **Análise de produtos:**
  - [ ] Histórico de compra por produto
  - [ ] "Você compra arroz a cada 15 dias"
  - [ ] Detectar aumento de preço
  - [ ] Sugestões de economia baseadas em itens
- [ ] Armazenar imagem da nota fiscal
- [ ] Funciona offline (processa quando conectar)

### Simulador de Cenários Financeiros
- [ ] **Simular mudanças no orçamento:**
  - [ ] "E se eu cancelar Netflix e Spotify?"
  - [ ] "E se eu trocar de carro?"
  - [ ] "E se eu mudar de emprego?"
  - [ ] "E se eu quitar uma dívida?"
- [ ] **Tipos de simulação:**
  - [ ] Cancelar/adicionar despesa recorrente
  - [ ] Alterar valor de receita (salário)
  - [ ] Adicionar/remover dívida
  - [ ] Mudar categoria de gastos variáveis
  - [ ] Cenário de emergência (perder emprego)
- [ ] **Visualização de impacto:**
  - [ ] Comparação lado a lado (atual vs simulado)
  - [ ] Impacto mensal e anual
  - [ ] Quanto economiza/perde por mês
  - [ ] Como afeta metas de economia
  - [ ] Projeção de saldo futuro
- [ ] **Simulações predefinidas:**
  - [ ] "Modo economia extrema" (corta tudo que pode)
  - [ ] "Modo investidor" (aumenta poupança ao máximo)
  - [ ] "Modo quitação de dívidas" (prioriza pagar tudo)
- [ ] Salvar cenários favoritos
- [ ] Comparar múltiplos cenários
- [ ] Aplicar cenário ao orçamento real

### Lista de Compras Inteligente
- [ ] **Criar lista de compras:**
  - [ ] Adicionar produtos manualmente
  - [ ] Sugestões baseadas em histórico
  - [ ] Vincular ao orçamento de categoria
  - [ ] Definir limite de gastos
- [ ] **Controle em tempo real:**
  - [ ] Ir marcando produtos comprados
  - [ ] Somar total conforme adiciona
  - [ ] Alerta se estourar orçamento
  - [ ] "Você tem R$ 50 restantes"
- [ ] **Integração com orçamento:**
  - [ ] "Você tem R$ 300 disponíveis em Alimentação"
  - [ ] Calcula saldo após compras
  - [ ] Sugere ajustes se ultrapassar
- [ ] **Sugestões inteligentes:**
  - [ ] "Você costuma comprar arroz todo mês"
  - [ ] "Papel higiênico está acabando (comprou há 25 dias)"
  - [ ] Baseado em frequência de compra
- [ ] **Finalizar compra:**
  - [ ] Criar transação automaticamente
  - [ ] Categoria e valor já preenchidos
  - [ ] Vincular à conta
  - [ ] Opção de escanear nota depois
- [ ] Múltiplas listas (mercado, farmácia, feira)
- [ ] Compartilhar lista (família)
- [ ] Histórico de listas antigas

---

## Tecnologias Sugeridas

### Backend
- **Opção 1:** Node.js + Express + PostgreSQL/MongoDB
- **Opção 2:** Python + Django/FastAPI + PostgreSQL
- **Opção 3:** .NET Core + SQL Server

### Frontend Web
- **Opção 1:** React + TypeScript + Tailwind CSS
- **Opção 2:** Vue.js + Vuetify
- **Opção 3:** Next.js (React com SSR)

### Mobile
- **Opção 1:** React Native (código compartilhado)
- **Opção 2:** Flutter (performance nativa)
- **Opção 3:** Native (Swift/Kotlin) - melhor integração com push

### Notificações Push
- Firebase Cloud Messaging (FCM)
- OneSignal
- AWS SNS

### Banco de Dados
- PostgreSQL (relacional, robusto)
- MongoDB (flexível, NoSQL)
- SQLite (local, sincronização)

---

## Arquitetura

```
┌─────────────────┐         ┌─────────────────┐
│   Web App       │         │   Mobile App    │
│   (React/Vue)   │         │  (React Native) │
└────────┬────────┘         └────────┬────────┘
         │                           │
         │    API REST/GraphQL       │
         └───────────┬───────────────┘
                     │
         ┌───────────▼───────────┐
         │   Backend Server      │
         │   (Node/Python/.NET)  │
         └───────────┬───────────┘
                     │
         ┌───────────▼───────────┐
         │   Database            │
         │   (PostgreSQL/Mongo)  │
         └───────────────────────┘

         ┌───────────────────────┐
         │   Push Notification   │
         │   Service (FCM)       │
         └───────────────────────┘
```

---

## Indicadores Visuais no Site Web - Transações Pendentes

### Elementos Chamativos

**1. Badge no Menu/Navbar (Sempre visível)**
```
┌────────────────────────────────────────┐
│  Tony Save Your Finances              │
├────────────────────────────────────────┤
│  [🏠 Dashboard]  [💰 Transações (5)]  │
│                      ↑                 │
│              Badge vermelho pulsando   │
└────────────────────────────────────────┘
```

**2. Banner de Alerta no Topo (Fixo até resolver)**
```
┌──────────────────────────────────────────────┐
│  ⚠️ ATENÇÃO! Você tem 5 transações não      │
│  categorizadas                               │
│  [Categorizar Agora]  [Lembrar Depois]      │
└──────────────────────────────────────────────┘
// Cor: Amarelo/Laranja chamativo
// Animação: Pulso suave a cada 3 segundos
```

**3. Card Destacado no Dashboard**
```
┌────────────────────────────────────────────┐
│  ⚡ AÇÃO NECESSÁRIA                        │
├────────────────────────────────────────────┤
│                                            │
│  🔴 5 transações aguardando categorização │
│                                            │
│  Última capturada: há 2 horas              │
│  • R$ 47,90 - MERCADO EXTRA                │
│  • R$ 85,00 - POSTO SHELL                  │
│  • R$ 15,00 - UBER                         │
│  • R$ 120,00 - FARMACIA SAO PAULO          │
│  • R$ 200,00 - PIX RECEBIDO                │
│                                            │
│  [Categorizar Todas]                       │
└────────────────────────────────────────────┘
// Cor: Gradiente vermelho/laranja
// Borda: Animação pulsante
// Posição: Topo do dashboard, antes de tudo
```

**4. Seção Dedicada com Lista Interativa**
```
┌─────────────────────────────────────────────────────┐
│  📋 TRANSAÇÕES PENDENTES (5)                        │
├─────────────────────────────────────────────────────┤
│                                                     │
│  ┌────────────────────────────────────────────┐    │
│  │ 🔴 R$ 47,90 - MERCADO EXTRA                │    │
│  │ Hoje às 14:32 • Nubank                     │    │
│  │ [🍔 Alimentação] [🚗 Transporte] [🎮 Lazer]│    │
│  └────────────────────────────────────────────┘    │
│                                                     │
│  ┌────────────────────────────────────────────┐    │
│  │ 🔴 R$ 85,00 - POSTO SHELL                  │    │
│  │ Hoje às 12:15 • Nubank                     │    │
│  │ [🍔 Alimentação] [🚗 Transporte] [🎮 Lazer]│    │
│  └────────────────────────────────────────────┘    │
│                                                     │
│  [+ Ver todas as 5 transações]                      │
└─────────────────────────────────────────────────────┘
// Cada card tem hover com sombra
// Categorização inline (1 clique)
```

**5. Notificação Toast (Popup temporário)**
```
┌──────────────────────────────┐
│  🔔 Nova transação capturada │
│  R$ 47,90 - MERCADO EXTRA    │
│  [Categorizar] [Depois]      │
└──────────────────────────────┘
// Aparece no canto superior direito
// Fica 8 segundos na tela
// Som opcional
```

**6. Contador no Ícone do Site (Favicon)**
```
🔴 (5)  ← Badge no favicon/ícone da aba
Tony Save Your Finances
```

### Interface Completa - Exemplo Dashboard

```
┌───────────────────────────────────────────────────────┐
│  ⚠️ 5 transações não categorizadas [Categorizar]     │ ← Banner fixo topo
├───────────────────────────────────────────────────────┤
│                                                       │
│  Tony Save  [Dashboard] [💰 Transações (5)] [Relat.] │ ← Badge menu
│                                  ↑ Vermelho pulsando  │
│                                                       │
│  ┌─────────────────────────────────────────────┐    │
│  │  ⚡ AÇÃO NECESSÁRIA - 5 Pendentes           │    │ ← Card destacado
│  │                                              │    │
│  │  🔴 R$ 47,90 - MERCADO EXTRA                │    │
│  │  🔴 R$ 85,00 - POSTO SHELL                  │    │
│  │  🔴 R$ 15,00 - UBER                         │    │
│  │                                              │    │
│  │  [Categorizar Agora]                        │    │
│  └─────────────────────────────────────────────┘    │
│                                                       │
│  📊 Resumo Mensal                                    │
│  ┌─────────────────────────────────────────────┐    │
│  │  Receitas: R$ 4.000,00                      │    │
│  │  Despesas: R$ 2.273,00                      │    │
│  │  Saldo: R$ 1.727,00                         │    │
│  └─────────────────────────────────────────────┘    │
│                                                       │
│  💰 Orçamento do Mês                                 │
│  [Gráficos...]                                       │
└───────────────────────────────────────────────────────┘
```

### Opções de Estilo Visual

**Cores sugeridas:**
- 🔴 Vermelho: #EF4444 (urgente, não categorizado)
- 🟡 Amarelo: #FBBF24 (atenção)
- 🟢 Verde: #10B981 (tudo ok)

**Animações:**
- **Pulso:** Badge cresce/diminui suavemente (1.5s loop)
- **Shake:** Banner balança de leve quando nova transação chega
- **Glow:** Brilho ao redor do card principal

**Estados:**
- Nova transação (< 1h): Borda vermelha + pulso rápido
- Antiga (> 24h): Borda laranja + pulso lento
- Muito antiga (> 3 dias): Borda vermelha escura + alerta crítico

### Comportamento Responsivo

**Desktop:**
- Banner fixo no topo
- Card grande no dashboard
- Lista expandida com todas as transações

**Mobile:**
- Badge no ícone do app
- Banner compacto (apenas contador)
- Card menor, mostra só as 3 mais recentes
- Botão flutuante fixo: [Categorizar (5)]

### Persistência do Alerta

```
Se transações pendentes > 0:
  ✓ Banner sempre visível no topo
  ✓ Badge permanente no menu
  ✓ Card prioritário no dashboard
  ✓ Push notification 1x ao dia

Se todas categorizadas:
  ✓ Banner desaparece
  ✓ Badge removido
  ✓ Card substituído por "Tudo em dia! ✅"
```

---

## Fluxo de Captura Automática de Transações

### Exemplo: Compra com Cartão

1. **Transação real:** Você compra algo com cartão de crédito/débito
2. **Notificação bancária:** Banco envia notificação padrão
   ```
   "Nubank: Compra aprovada
   R$ 47,90 - MERCADO EXTRA
   às 14:32"
   ```
3. **Captura automática:** App detecta e lê a notificação
4. **Parsing inteligente:** Extrai dados estruturados:
   - Valor: R$ 47,90
   - Estabelecimento: MERCADO EXTRA
   - Data/Hora: hoje às 14:32
   - Banco/Cartão: Nubank
5. **Criação da transação:** Salva automaticamente como "Pendente de categorização"
6. **Notificação interna:** "Nova transação capturada! Toque para categorizar"
7. **Categorização rápida:** Usuário escolhe categoria (ex: Alimentação)
8. **Confirmação:** Transação finalizada e sincronizada

### Vantagens
- ✅ Zero esforço para registrar gastos
- ✅ Dados já preenchidos (valor, hora, local)
- ✅ Funciona com qualquer banco/cartão que envie notificações
- ✅ Categorização posterior quando tiver tempo
- ✅ Histórico completo sem esquecer nenhuma compra

---

## Fluxo de Gestão de Dívidas

### Exemplo 1: Você deve a alguém

**Situação:** Você combinou de pagar R$ 200 pro João na sexta-feira

1. **Registro rápido:**
   - Tipo: Dívida a pagar
   - Valor: R$ 200,00
   - Pessoa: João
   - Deadline: 10/01/2026 (sexta)
   - Descrição: "Empréstimo pra consertar carro"
   - **Chave PIX:** (11) 98765-4321

2. **Sistema registra:**
   - Cria uma "dívida pendente"
   - Adiciona ao saldo devedor
   - Agenda notificação
   - Armazena dados de pagamento

3. **Notificações automáticas:**
   - 2 dias antes: "Lembre-se: R$ 200 pro João em 2 dias"
   - No dia: "Hoje você precisa pagar R$ 200 pro João"
   - Após vencimento: "Dívida vencida: R$ 200 pro João"

4. **Pagamento facilitado:**
   - Abre a dívida no app
   - Botão **"Copiar PIX"** → copia (11) 98765-4321
   - Cola direto no app do banco
   - Paga e anexa comprovante
   - Marca como "Quitada"
   - Atualiza saldo automaticamente

### Exemplo 2: Alguém deve a você

**Situação:** Você emprestou R$ 50 pra Maria, ela vai te pagar até terça

1. **Registro:**
   - Tipo: Empréstimo a receber
   - Valor: R$ 50,00
   - Pessoa: Maria
   - Deadline: 07/01/2026
   - Descrição: "Emprestei pro almoço"
   - **Sua chave PIX (para ela te pagar):** seuemail@gmail.com

2. **Acompanhamento:**
   - Aparece como "a receber"
   - Notificação educada próximo do prazo
   - Histórico de cobranças (se precisar remarcar)

3. **Facilitar cobrança:**
   - Botão **"Compartilhar dados"** → envia mensagem automática
   - Exemplo: "Oi Maria! Lembrete: R$ 50,00 até 07/01. PIX: seuemail@gmail.com"
   - Ou copia só a chave PIX pra mandar

### Exemplo 3: Pagamento Parcial

**Situação:** Você deve R$ 500 e vai pagar em 2x

1. **Registro inicial:** R$ 500 pro Pedro até 15/01
2. **Primeiro pagamento:** R$ 250 em 08/01
   - Sistema atualiza: Falta R$ 250
   - Status: "Paga parcialmente"
3. **Segundo pagamento:** R$ 250 em 15/01
   - Sistema marca: "Quitada"
   - Histórico completo dos pagamentos

### Exemplo 4: Dívida com Entidade/Empresa

**Situação:** Você comprou móveis na loja e vai pagar direto pra eles em 3x

1. **Registro:**
   - Tipo: Dívida a pagar
   - **Entidade:** Magazine Luiza
   - Valor total: R$ 1.500,00
   - Parcelas: 3x de R$ 500,00
   - Deadlines: 15/01, 15/02, 15/03
   - Descrição: "Compra de sofá e mesa"
   - **Chave PIX:** 12.345.678/0001-99 (CNPJ)
   - **Código de barras:** 23793.38128.60000.123456.789012.3456.78

2. **Acompanhamento automático:**
   - Cria 3 lembretes separados
   - Cada pagamento é registrado individualmente
   - Botão **"Copiar PIX"** ou **"Copiar código de barras"**
   - Anexar boletos/comprovantes

3. **Casos de uso:**
   - Carnê de loja
   - Prestação de serviço (dentista, mecânico)
   - Mensalidade de curso/academia
   - Aluguel para imobiliária
   - Contas recorrentes (água, luz, internet)

### Exemplo 5: Empréstimo Recebido de Entidade

**Situação:** Você pegou um empréstimo no banco cooperativo

1. **Registro:**
   - Tipo: Dívida a pagar
   - **Entidade:** Sicredi
   - Valor: R$ 5.000,00
   - Parcelas: 12x de R$ 450,00 (com juros)
   - Primeira parcela: 20/01/2026
   - Juros: 2% ao mês
   - Observação: "Empréstimo pessoal - contrato #12345"

### Interface Sugerida

**Dashboard de Dívidas:**
```
┌──────────────────────────────────────────────┐
│  💰 DÍVIDAS E EMPRÉSTIMOS                   │
├──────────────────────────────────────────────┤
│                                              │
│  A PAGAR - PESSOAS                           │
│  🔴 R$ 200 - João (vence em 2 dias)          │
│  🟢 R$ 100 - Carlos (vence em 10 dias)       │
│                                              │
│  A PAGAR - ENTIDADES                         │
│  🔴 R$ 500 - Magazine Luiza (vence amanhã)   │
│  🟡 R$ 450 - Sicredi (vence em 5d)           │
│  🟢 R$ 800 - Imobiliária XYZ (vence em 12d)  │
│                                              │
│  A RECEBER - PESSOAS                         │
│  🟢 R$ 50 - Maria (vence amanhã)             │
│  🟡 R$ 300 - Pedro (vence em 7d)             │
│                                              │
│  ─────────────────────────────────────────   │
│  Total devendo: R$ 2.050                     │
│  Total a receber: R$ 350                     │
│  Saldo líquido: -R$ 1.700                    │
└──────────────────────────────────────────────┘
```

**Tela de Cadastro Rápido:**
```
┌─────────────────────────────────────────┐
│  Nova Dívida/Empréstimo                 │
├─────────────────────────────────────────┤
│                                         │
│  Tipo: ⚪ A Pagar  ⚪ A Receber         │
│                                         │
│  Atribuir a:                            │
│  ⚫ Pessoa      ⚪ Entidade              │
│                                         │
│  Nome: [João Silva                   ▼] │
│         Sugestões:                      │
│         - João Silva                    │
│         - João Pedro                    │
│         + Adicionar novo                │
│                                         │
│  Valor: R$ [___________]                │
│                                         │
│  Vencimento: [10/01/2026]               │
│                                         │
│  Parcelas: [1▼] ou [3x sem juros]       │
│                                         │
│  ─── Dados de Pagamento ────            │
│                                         │
│  Chave PIX: [(11) 98765-4321        ]   │
│             ⚪ CPF  ⚪ Cel  ⚫ Email     │
│             ⚪ CNPJ ⚪ Aleatória         │
│                                         │
│  Ou dados bancários:                    │
│  Banco: [___] Ag: [____] Conta: [____]  │
│                                         │
│  Ou código de barras/QR Code:           │
│  [_________________________________]    │
│  📷 Escanear QR Code                    │
│                                         │
│  ─────────────────────────               │
│                                         │
│  Descrição: [________________]          │
│                                         │
│  📎 Anexar comprovante/boleto           │
│                                         │
│  [Cancelar]      [Salvar Dívida]        │
└─────────────────────────────────────────┘
```

**Tela de Visualização da Dívida:**
```
┌─────────────────────────────────────────┐
│  💰 Dívida: João Silva                  │
├─────────────────────────────────────────┤
│                                         │
│  Valor: R$ 200,00                       │
│  Vence: 10/01/2026 (em 8 dias) 🟢      │
│  Status: Pendente                       │
│                                         │
│  Descrição:                             │
│  "Empréstimo pra consertar carro"       │
│                                         │
│  ─── Dados de Pagamento ────            │
│                                         │
│  Chave PIX (Celular):                   │
│  (11) 98765-4321                        │
│  [📋 Copiar PIX]                        │
│                                         │
│  ─────────────────────────               │
│                                         │
│  [Marcar como Paga]                     │
│  [Pagar Parcialmente]                   │
│  [Adiar Vencimento]                     │
│  [Editar]  [Excluir]                    │
│                                         │
└─────────────────────────────────────────┘
```

### Vinculação de Transações com Dívidas

**Opção 1: Marcar como Paga (Cria transação automaticamente)**
```
┌─────────────────────────────────────────┐
│  ✅ Registrar Pagamento                │
├─────────────────────────────────────────┤
│  Dívida: João Silva                     │
│  Valor total: R$ 200,00                 │
│                                         │
│  Tipo de pagamento:                     │
│  ⚫ Pagamento total (R$ 200,00)         │
│  ⚪ Pagamento parcial                   │
│                                         │
│  💡 Isso criará uma TRANSAÇÃO           │
│  de despesa na sua conta                │
│                                         │
│  Conta de origem:                       │
│  [Conta Corrente Nubank ▼]             │
│  Saldo atual: R$ 1.500,00               │
│  Saldo após: R$ 1.300,00                │
│                                         │
│  Data do pagamento:                     │
│  [10/01/2026 📅] Hoje                  │
│                                         │
│  Categoria da despesa:                  │
│  [Empréstimos/Dívidas ▼]               │
│                                         │
│  Comprovante (opcional):                │
│  [📎 Anexar]                            │
│                                         │
│  ─────────────────────────               │
│                                         │
│  O que acontecerá:                      │
│  ✓ Dívida marcada como "Quitada"        │
│  ✓ Transação criada: -R$ 200            │
│  ✓ Saldo atualizado na conta            │
│  ✓ Transação vinculada à dívida         │
│                                         │
│  [Cancelar]        [Confirmar Pagamento]│
└─────────────────────────────────────────┘
```

**Opção 2: Vincular transação existente**
```
┌─────────────────────────────────────────┐
│  🔗 Vincular Transação Existente       │
├─────────────────────────────────────────┤
│  Dívida: João Silva - R$ 200,00         │
│                                         │
│  Selecione uma transação para vincular: │
│                                         │
│  ⚫ 10/Jan - PIX para João               │
│     R$ -200,00 • Conta Nubank           │
│     Categoria: Outras despesas          │
│                                         │
│  ⚪ 08/Jan - Transferência               │
│     R$ -200,00 • Conta Nubank           │
│     Categoria: Transferências           │
│                                         │
│  ⚪ 05/Jan - Pagamento                   │
│     R$ -200,00 • PicPay                 │
│     Categoria: Outras despesas          │
│                                         │
│  💡 A transação será vinculada e a      │
│  dívida marcada como paga               │
│                                         │
│  [Cancelar]          [Vincular]         │
└─────────────────────────────────────────┘
```

**Tela de dívida após pagamento:**
```
┌─────────────────────────────────────────┐
│  💰 Dívida: João Silva                  │
├─────────────────────────────────────────┤
│                                         │
│  Valor: R$ 200,00                       │
│  Vencimento: 10/01/2026                 │
│  Status: ✅ Quitada (10/Jan/2026)      │
│                                         │
│  Descrição:                             │
│  "Empréstimo pra consertar carro"       │
│                                         │
│  ─── Pagamento Registrado ────          │
│                                         │
│  📅 Pago em: 10/01/2026                │
│  💰 Valor: R$ 200,00                    │
│  🏦 Conta: Conta Corrente Nubank        │
│                                         │
│  🔗 Transação vinculada:                │
│  [Ver Transação #1234]                  │
│                                         │
│  📎 Comprovante: [comprovante.pdf]      │
│                                         │
│  ─────────────────────────               │
│                                         │
│  [Editar]  [Excluir]                    │
│                                         │
└─────────────────────────────────────────┘
```

**Dívida parcelada com múltiplos pagamentos:**
```
┌─────────────────────────────────────────┐
│  💰 Dívida: Magazine Luiza              │
├─────────────────────────────────────────┤
│  Valor total: R$ 1.500,00               │
│  Parcelas: 3x de R$ 500,00              │
│  Status: 🟡 Paga parcialmente (2/3)    │
│                                         │
│  ─── Histórico de Pagamentos ────       │
│                                         │
│  ✅ Parcela 1/3 - R$ 500,00            │
│     Pago em: 15/01/2026                 │
│     Conta: Nubank                       │
│     🔗 [Ver Transação #1145]            │
│     📎 [boleto1.pdf]                    │
│                                         │
│  ✅ Parcela 2/3 - R$ 500,00            │
│     Pago em: 15/02/2026                 │
│     Conta: Nubank                       │
│     🔗 [Ver Transação #1289]            │
│     📎 [boleto2.pdf]                    │
│                                         │
│  ⏳ Parcela 3/3 - R$ 500,00            │
│     Vence: 15/03/2026 (em 5 dias)       │
│     [Marcar como Paga]                  │
│                                         │
│  ─────────────────────────               │
│  Pago: R$ 1.000,00                      │
│  Falta: R$ 500,00                       │
│  ─────────────────────────               │
│                                         │
│  [Editar]  [Excluir]                    │
└─────────────────────────────────────────┘
```

**Visualização da transação com vínculo:**
```
┌─────────────────────────────────────────┐
│  💸 Transação #1234                    │
├─────────────────────────────────────────┤
│  Tipo: Despesa                          │
│  Valor: -R$ 200,00                      │
│  Data: 10/01/2026                       │
│                                         │
│  Descrição: Pagamento João Silva        │
│  Categoria: Empréstimos/Dívidas         │
│                                         │
│  Conta: Conta Corrente Nubank           │
│  Saldo antes: R$ 1.500,00               │
│  Saldo depois: R$ 1.300,00              │
│                                         │
│  ─── Vinculada a Dívida ────            │
│  🔗 Dívida: João Silva                  │
│     Valor total: R$ 200,00              │
│     Status: ✅ Quitada                 │
│     [Ver Dívida Completa]               │
│                                         │
│  ─────────────────────────               │
│                                         │
│  📎 Comprovante: [pix_joao.jpg]         │
│                                         │
│  [Editar]  [Excluir]                    │
└─────────────────────────────────────────┘
```

**Extrato da conta mostrando transação vinculada:**
```
┌────────────────────────────────────────────────────────┐
│  💰 Extrato - Conta Corrente Nubank                   │
├────────────────────────────────────────────────────────┤
│  Saldo atual: R$ 1.300,00                             │
│  Período: Janeiro/2026                                 │
│                                                        │
│  05/Jan 🟢 Salário recebido                           │
│  +R$ 3.000,00                    Saldo: R$ 4.500,00   │
│  Receita • Trabalho                                   │
│                                                        │
│  08/Jan 🔴 Aluguel                                    │
│  -R$ 1.200,00                    Saldo: R$ 3.300,00   │
│  Despesa • Moradia                                    │
│                                                        │
│  10/Jan 🔴 Pagamento João Silva 🔗                    │
│  -R$ 200,00                      Saldo: R$ 3.100,00   │
│  Despesa • Empréstimos/Dívidas                        │
│  💡 Vinculado à dívida "João Silva"                    │
│  [Ver Dívida]                                          │
│                                                        │
│  12/Jan 🔴 Mercado Extra                              │
│  -R$ 350,00                      Saldo: R$ 2.750,00   │
│  Despesa • Alimentação                                │
│                                                        │
│  [Exportar PDF] [Filtrar Categoria]                   │
└────────────────────────────────────────────────────────┘
```

---

## Sistema de Orçamento Inteligente - Detalhamento

### Como Funciona

**1. Primeiro uso - Sugestão baseada em método:**
- Usuário registra receitas do mês:
  - Salário: R$ 3.000,00
  - Freelance: R$ 800,00
  - Venda no Mercado Livre: R$ 200,00
  - **Total de incomings: R$ 4.000,00**
- Sistema pergunta: "Qual método de orçamento prefere?"
- Usuário escolhe: Regra 50-30-20
- Sistema sugere automaticamente:

```
┌──────────────────────────────────────────────┐
│  💡 SUGESTÃO DE ORÇAMENTO (50-30-20)        │
├──────────────────────────────────────────────┤
│  Receitas totais do mês: R$ 4.000,00         │
│                                              │
│  Fontes de renda:                            │
│  • Salário: R$ 3.000,00                      │
│  • Freelance: R$ 800,00                      │
│  • Vendas: R$ 200,00                         │
│                                              │
│  🏠 ESSENCIAIS (50%) - R$ 2.000,00          │
│     - Alimentação essencial: R$ 800         │
│     - Moradia (aluguel/água/luz): R$ 800    │
│     - Transporte: R$ 250                    │
│     - Saúde: R$ 150                         │
│                                              │
│  🎯 DESEJOS (30%) - R$ 1.200,00             │
│     - Lazer/Entretenimento: R$ 500          │
│     - Alimentação não-essencial: R$ 400     │
│     - Compras pessoais: R$ 300              │
│                                              │
│  💰 POUPANÇA/INVEST (20%) - R$ 800,00       │
│     - Reserva de emergência: R$ 500         │
│     - Investimentos: R$ 300                 │
│                                              │
│  [Aceitar]  [Personalizar]  [Outro método]  │
└──────────────────────────────────────────────┘
```

**2. Após 2-3 meses de uso - Análise e ajuste:**

Sistema analiza padrões reais (considerando receita variável):
```
Histórico de receitas (últimos 3 meses):
Mês 1: R$ 4.000,00 (Salário + Freelance + Vendas)
Mês 2: R$ 3.500,00 (Salário + Freelance)
Mês 3: R$ 4.200,00 (Salário + Freelance + Vendas + Bônus)
Média mensal: R$ 3.900,00

Histórico de gastos (últimos 3 meses):
- Alimentação: R$ 950 (24% da média)
- Transporte: R$ 450 (12%)
- Moradia: R$ 800 (21%)
- Lazer: R$ 300 (8%)
- Saúde: R$ 150 (4%)
- Outros: R$ 200 (5%)
- Poupança: R$ 150 (4%)
```

**Sistema sugere ajuste:**
```
┌──────────────────────────────────────────────┐
│  🤖 SUGESTÃO PERSONALIZADA                  │
├──────────────────────────────────────────────┤
│  Analisamos seus últimos 3 meses!           │
│                                              │
│  ⚠️ DIVERGÊNCIAS ENCONTRADAS:               │
│                                              │
│  Alimentação:                                │
│  Planejado: R$ 600 (20%)                     │
│  Real: R$ 950 (32%) ⬆️ +12%                 │
│  💡 Sugestão: Ajustar para R$ 900 (30%)     │
│                                              │
│  Poupança:                                   │
│  Planejado: R$ 600 (20%)                     │
│  Real: R$ 150 (5%) ⬇️ -15%                  │
│  💡 Sugestão: Ajustar para R$ 300 (10%)     │
│                                              │
│  ── NOVO ORÇAMENTO SUGERIDO ──               │
│                                              │
│  Alimentação: 30% (R$ 900) ⬆️               │
│  Moradia: 27% (R$ 810) ✓                    │
│  Transporte: 15% (R$ 450) ✓                 │
│  Lazer: 10% (R$ 300) ✓                      │
│  Saúde: 8% (R$ 240) ⬆️                      │
│  Poupança: 10% (R$ 300) ⬇️                  │
│                                              │
│  [Aplicar Ajustes]  [Manter Atual]          │
└──────────────────────────────────────────────┘
```

### Exemplo 3: Alertas em Tempo Real

Durante o mês, quando o usuário está gastando:

```
┌──────────────────────────────────────────┐
│  ⚠️ ALERTA DE ORÇAMENTO                 │
├──────────────────────────────────────────┤
│  Categoria: Alimentação                  │
│                                          │
│  Limite mensal: R$ 900,00                │
│  Gasto até agora: R$ 720,00 (80%)        │
│  Restante: R$ 180,00                     │
│                                          │
│  📅 Faltam 8 dias para o fim do mês      │
│                                          │
│  💡 Dica: Você tem R$ 22,50/dia          │
│                                          │
│  [OK]  [Ajustar Limite]                  │
└──────────────────────────────────────────┘
```

### Exemplo 4: Dashboard com Orçamento

```
┌────────────────────────────────────────────────────┐
│  📊 ORÇAMENTO DO MÊS - Janeiro 2026               │
├────────────────────────────────────────────────────┤
│                                                    │
│  Alimentação Essencial                             │
│  ████████████░░░░░░░░ 65% (R$ 585 / R$ 900)       │
│  🟢 Dentro do orçamento                           │
│                                                    │
│  Transporte                                        │
│  ███████████████████░ 95% (R$ 428 / R$ 450)       │
│  🟡 Atenção, próximo do limite                    │
│                                                    │
│  Lazer                                             │
│  ██████████████████████ 110% (R$ 330 / R$ 300)    │
│  🔴 Ultrapassou! +R$ 30                           │
│                                                    │
│  Moradia (Fixo)                                    │
│  ████████████████████ 100% (R$ 810 / R$ 810)      │
│  ✓ Pago                                           │
│                                                    │
│  Poupança                                          │
│  ████████░░░░░░░░░░░░ 40% (R$ 120 / R$ 300)       │
│  💡 Tente guardar mais R$ 180                     │
│                                                    │
│  ─────────────────────────────────────────────     │
│  Total gasto: R$ 2.273 / R$ 3.000                  │
│  Disponível: R$ 727                                │
│  Meta de poupança do mês: 60% pendente             │
└────────────────────────────────────────────────────┘
```

### Categorias Inteligentes

**Essenciais (Não podem ser cortados):**
- Alimentação básica
- Moradia (aluguel, IPTU)
- Contas (água, luz, internet)
- Transporte para trabalho
- Saúde/Medicamentos
- Dívidas

**Desejos (Podem ser ajustados):**
- Lazer/Entretenimento
- Restaurantes
- Roupas/Acessórios
- Assinaturas (streaming, etc)
- Hobbies

**Poupança/Investimento:**
- Reserva de emergência
- Investimentos
- Metas de longo prazo

### Lógica de Ajuste Automático

```javascript
// Exemplo de como o sistema ajusta

1. Analisa últimos 3 meses
2. Calcula média de gasto por categoria
3. Identifica categorias que desviam >10% do planejado
4. Para categorias essenciais: sugere aumentar limite
5. Para desejos: sugere reduzir ou manter
6. Para poupança: ajusta baseado no que "sobra" realmente
7. Mantém proporção entre essenciais/desejos/poupança
```

### Métodos de Orçamento Disponíveis

**1. Regra 50-30-20:**
- 50% Necessidades
- 30% Desejos
- 20% Poupança/Investimentos

**2. Regra 70-20-10:**
- 70% Despesas gerais
- 20% Poupança
- 10% Investimentos/Doações

**3. Método Kakebo (Japonês):**
- Sobrevivência (alimentação, moradia)
- Opcional (lazer, restaurantes)
- Cultura (livros, cursos)
- Extra (presentes, imprevistos)

**4. Orçamento Base Zero:**
- Toda receita é alocada
- Receita - Despesas - Poupança = 0

### Tratamento de Renda Variável

**Para quem tem receita instável (freelancers, vendedores, autônomos):**

```
┌──────────────────────────────────────────────┐
│  💼 ORÇAMENTO COM RENDA VARIÁVEL            │
├──────────────────────────────────────────────┤
│  Sistema calcula baseado em:                 │
│                                              │
│  Opção 1: Média dos últimos 3 meses          │
│  Mês 1: R$ 4.000                             │
│  Mês 2: R$ 3.500                             │
│  Mês 3: R$ 4.200                             │
│  → Orçamento: R$ 3.900 (média)               │
│                                              │
│  Opção 2: Renda mínima garantida             │
│  Salário fixo: R$ 3.000                      │
│  → Orçamento: R$ 3.000 (conservador)         │
│  → Extras vão direto pra poupança            │
│                                              │
│  Opção 3: Projeção pessimista                │
│  Menor valor dos últimos 6 meses             │
│  → Orçamento: R$ 3.200                       │
│                                              │
│  💡 Recomendado: Opção 2 (conservador)       │
│  Garante que você não vai passar aperto      │
│  nos meses ruins                             │
└──────────────────────────────────────────────┘
```

**Exemplo prático - Freelancer:**

**Mês com alta renda (R$ 5.000):**
- Orçamento base: R$ 3.000
- Excedente: R$ 2.000
- Sistema sugere: "Guardar R$ 1.500, pode gastar R$ 500 extras"

**Mês com baixa renda (R$ 2.800):**
- Orçamento base: R$ 3.000
- Déficit: -R$ 200
- Sistema alerta: "Receita abaixo do orçamento. Use reserva ou ajuste gastos"

**Benefícios:**
✅ Segurança nos meses ruins
✅ Poupança acelerada nos meses bons
✅ Previne endividamento
✅ Cria colchão financeiro

---

## Sistema de Push Notifications para Orçamento

### Tipos de Alertas

**1. Alerta de 80% (Preventivo)**
```
┌─────────────────────────────────────┐
│  🟡 Tony Save - Atenção!           │
├─────────────────────────────────────┤
│  Você já gastou 80% do orçamento   │
│  de Alimentação                     │
│                                     │
│  Gasto: R$ 720 / R$ 900             │
│  Restante: R$ 180                   │
│                                     │
│  📅 Faltam 8 dias no mês            │
└─────────────────────────────────────┘
[Toque para ver detalhes]
```

**2. Alerta de Estouro de Categoria**
```
┌─────────────────────────────────────┐
│  🔴 Tony Save - Orçamento Estourado│
├─────────────────────────────────────┤
│  Categoria: Lazer                   │
│                                     │
│  Limite: R$ 300,00                  │
│  Gasto: R$ 330,00                   │
│  Excedente: +R$ 30,00               │
│                                     │
│  💡 Considere ajustar seus gastos   │
└─────────────────────────────────────┘
[Ver orçamento] [Ignorar]
```

**3. Alerta de Estouro Geral**
```
┌─────────────────────────────────────┐
│  🔴 Tony Save - ALERTA CRÍTICO!    │
├─────────────────────────────────────┤
│  Você ultrapassou o orçamento       │
│  total do mês!                      │
│                                     │
│  Orçamento: R$ 3.000,00             │
│  Gasto: R$ 3.150,00                 │
│  Excesso: -R$ 150,00                │
│                                     │
│  ⚠️ Você está no vermelho!         │
└─────────────────────────────────────┘
[Ver detalhes] [Ajustar orçamento]
```

**4. Alerta Preditivo (Ritmo de Gasto)**
```
┌─────────────────────────────────────┐
│  ⚠️ Tony Save - Alerta Preventivo  │
├─────────────────────────────────────┤
│  No ritmo atual, você vai estourar  │
│  o orçamento de Transporte          │
│                                     │
│  Gasto atual: R$ 350 (dia 15)       │
│  Projeção fim do mês: ~R$ 700       │
│  Limite: R$ 450                     │
│                                     │
│  💡 Reduza R$ 15/dia para não       │
│  ultrapassar                        │
└─────────────────────────────────────┘
[Entendi] [Ver sugestões]
```

**5. Alerta de Fim de Mês**
```
┌─────────────────────────────────────┐
│  📊 Tony Save - Resumo do Mês      │
├─────────────────────────────────────┤
│  Faltam 3 dias para o fim do mês!   │
│                                     │
│  Saldo disponível: R$ 427           │
│  Poupança pendente: R$ 180          │
│                                     │
│  💡 Tente guardar pelo menos        │
│  R$ 180 antes do dia 31!            │
└─────────────────────────────────────┘
[Ver detalhes] [Transferir agora]
```

**6. Notificação de Sucesso**
```
┌─────────────────────────────────────┐
│  ✅ Tony Save - Parabéns!          │
├─────────────────────────────────────┤
│  Você fechou o mês dentro do        │
│  orçamento!                         │
│                                     │
│  Gasto: R$ 2.820 / R$ 3.000         │
│  Poupança: R$ 180 ✓                 │
│                                     │
│  🎉 Continue assim!                 │
└─────────────────────────────────────┘
[Ver resumo mensal]
```

### Configurações de Notificação

```
┌─────────────────────────────────────────┐
│  🔔 Configurar Notificações            │
├─────────────────────────────────────────┤
│                                         │
│  Alertas de Orçamento:                  │
│  ☑️ Avisar ao atingir 80% (categoria)  │
│  ☑️ Avisar ao estourar categoria       │
│  ☑️ Avisar ao estourar orçamento geral │
│  ☑️ Alerta preditivo (ritmo de gasto)  │
│  ☐ Resumo semanal de gastos            │
│  ☑️ Resumo de fim de mês               │
│                                         │
│  Dívidas e Compromissos:                │
│  ☑️ Vencimento em 2 dias               │
│  ☑️ No dia do vencimento               │
│  ☑️ Após vencimento                    │
│                                         │
│  Transações:                            │
│  ☑️ Nova transação capturada           │
│  ☑️ Lembrete para categorizar          │
│                                         │
│  Horário de silêncio:                   │
│  De [22:00] até [08:00]                │
│                                         │
│  [Salvar Configurações]                 │
└─────────────────────────────────────────┘
```

### Lógica dos Alertas

**Alerta de 80% (Preventivo):**
```javascript
// Dispara quando gasto atinge 80% do limite
if (gastoCategoria >= limiteCategoria * 0.8 &&
    gastoCategoria < limiteCategoria) {
  enviarPush("Atenção! 80% do orçamento de {categoria}")
}
```

**Alerta de Estouro de Categoria:**
```javascript
// Dispara imediatamente quando ultrapassa
if (gastoCategoria > limiteCategoria) {
  enviarPush("🔴 Orçamento de {categoria} estourado!")
}
```

**Alerta de Estouro Geral:**
```javascript
// Dispara quando total de gastos > orçamento total
if (totalGastos > orcamentoTotal) {
  enviarPush("🔴 ALERTA: Orçamento geral estourado!")
}
```

**Alerta Preditivo:**
```javascript
// Calcula ritmo de gasto e projeta
diaAtual = 15
gastoAtual = 350
projecao = (gastoAtual / diaAtual) * 30 // ~700

if (projecao > limiteCategoria) {
  enviarPush("⚠️ No ritmo atual, você vai estourar {categoria}")
}
```

### Exemplos Práticos

**Cenário 1: Usuário comprando no mercado**
1. Faz compra de R$ 85 no mercado
2. Sistema atualiza: Alimentação = R$ 720 (80% de R$ 900)
3. **PUSH:** "🟡 Você já gastou 80% do orçamento de Alimentação"
4. Usuário vê no app: Restam R$ 180 pra 8 dias = R$ 22,50/dia

**Cenário 2: Usuário sai pra jantar**
1. Gasta R$ 80 no restaurante (categoria Lazer)
2. Total Lazer agora: R$ 330 (limite era R$ 300)
3. **PUSH:** "🔴 Orçamento de Lazer estourado! +R$ 30"
4. Usuário pode: Ver detalhes, Ajustar limite, ou Ignorar

**Cenário 3: Meio do mês**
1. Sistema analisa: Dia 15, gastou R$ 2.100
2. Projeção: R$ 4.200 até fim do mês
3. Orçamento total: R$ 3.000
4. **PUSH:** "⚠️ No ritmo atual, você vai estourar em R$ 1.200"
5. Sugestão: "Reduza gastos para R$ 30/dia"

**Cenário 4: Fim de mês bem-sucedido**
1. Dia 31 chega
2. Total gasto: R$ 2.820
3. Poupança atingida: R$ 180
4. **PUSH:** "✅ Parabéns! Você fechou no orçamento!"
5. Mostra resumo com conquistas

### Frequência de Notificações

```
┌────────────────────────────────────┐
│  Limites de Notificação:           │
├────────────────────────────────────┤
│  • Alerta 80%: 1x por categoria    │
│  • Estouro categoria: A cada R$ 50 │
│  • Estouro geral: 1x ao dia        │
│  • Preditivo: 1x por semana        │
│  • Fim de mês: Últimos 3 dias      │
│  • Dívidas: Conforme prazo         │
└────────────────────────────────────┘
```

---

## Sistema Unificado de Envelopes (Metas e Fundos) - Detalhamento

> **Decisão de Unificação (Janeiro/2026):**
> Anteriormente planejados como sistemas separados ("Metas de Economia" e "Reservas/Envelopes"), foram unificados em um único sistema de Envelopes com dois tipos: FUNDO e META.
>
> **Razão:** Ambos fazem a mesma coisa - separar dinheiro para objetivos específicos. Sistema unificado evita duplicação de código, confusão do usuário e facilita manutenção.

### Conceito Fundamental: Potes Separados com Saldo Real

**Envelopes NÃO são virtuais** - são "cofres separados" com saldo próprio.

**Exemplo:**
```
CONTAS:
├─ Nubank: R$ 5.000,00
└─ Carteira: R$ 300,00

ENVELOPES (saldo separado):
├─ 🚗 IPVA 2026: R$ 800,00
├─ 💻 Notebook: R$ 2.500,00
└─ 🏥 Emergência: R$ 1.000,00

PATRIMÔNIO TOTAL: R$ 9.600,00
```

**Depositar R$ 300 no envelope IPVA:**
- Conta Nubank: R$ 5.000 → R$ 4.700 (-R$ 300)
- Envelope IPVA: R$ 800 → R$ 1.100 (+R$ 300)
- Sistema cria 2 transações (saída da conta + entrada no envelope)

### Tipos de Envelope

#### 1. Envelope tipo FUNDO (Reservas Contínuas)
- **Uso:** Reservas recorrentes e despesas futuras
- **Exemplos:** IPVA, IPTU, emergência, férias, presentes
- **Comportamento:** Nunca finaliza automaticamente, continua acumulando
- **Alertas:** Quando saldo cai abaixo da meta

#### 2. Envelope tipo META (Objetivos de Compra)
- **Uso:** Economia para compra específica
- **Exemplos:** Notebook, viagem, carro, reforma
- **Comportamento:** Status muda para COMPLETO ao atingir 100%
- **Extras:** Vincula produto (imagem, URL, preço), rastreamento de preço
- **Gamificação:** Notificações em 25%, 50%, 75%, 100%

### Escolha do Tipo ao Criar

**Primeiro passo: escolher tipo de envelope**
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

### Criar Envelope tipo META

**Tela de cadastro (tipo META):**
```
┌────────────────────────────────────────────┐
│  🎯 Novo Envelope - META                  │
├────────────────────────────────────────────┤
│                                            │
│  Nome da meta:                             │
│  [Notebook Gamer Dell G15_______________]  │
│                                            │
│  Conta vinculada:                          │
│  [Nubank ▼]                                │
│                                            │
│  Valor da meta:                            │
│  R$ [5.000,00]                             │
│                                            │
│  Prazo desejado (opcional):                │
│  [31/10/2026      📅]                     │
│                                            │
│  ─── Informações do Produto (Opcional) ────│
│                                            │
│  Link de compra:                           │
│  [https://dell.com/notebook-g15_______]    │
│  🔗 Buscar informações automaticamente     │
│                                            │
│  📷 Imagem do produto:                     │
│  [Carregar imagem] ou [Capturar da URL]    │
│                                            │
│  ─── Depósito Automático (Opcional) ───    │
│                                            │
│  ☑️ Ativar depósito automático            │
│  Valor: R$ [500,00] ou [10] %             │
│  Frequência: [Mensal ▼]                    │
│  Dia: [5 ▼]                                │
│                                            │
│  Já economizou algum valor?                │
│  R$ [500,00] (depositar agora)             │
│                                            │
│  [Cancelar]          [Criar Meta 🎯]       │
└────────────────────────────────────────────┘
```

### Criar Envelope tipo FUNDO

**Tela de cadastro (tipo FUNDO):**
```
┌────────────────────────────────────────────┐
│  💰 Novo Envelope - FUNDO                 │
├────────────────────────────────────────────┤
│                                            │
│  Nome da reserva:                          │
│  [IPVA 2026__________________________]     │
│                                            │
│  Ícone:                                    │
│  ⚫ 🚗  ⚪ 🏥  ⚪ ✈️  ⚪ 🎁  ⚪ 💰         │
│                                            │
│  Conta vinculada:                          │
│  [Nubank ▼]                                │
│                                            │
│  Meta de valor:                            │
│  R$ [800,00]                               │
│                                            │
│  Data limite (opcional):                   │
│  [Março/2026 📅]                          │
│                                            │
│  ─── Depósito Automático (Opcional) ───    │
│                                            │
│  ☑️ Ativar depósito automático            │
│  Valor: R$ [200,00] ou [10] %             │
│  Frequência: [Mensal ▼]                    │
│  Dia: [5 ▼]                                │
│                                            │
│  Depositar agora:                          │
│  R$ [200,00]                               │
│                                            │
│  Observações:                              │
│  [Vencimento do IPVA em março______]       │
│                                            │
│  [Cancelar]        [Criar Fundo 💰]        │
└────────────────────────────────────────────┘
```

### Dashboard de Metas

```
┌──────────────────────────────────────────────────────┐
│  🎯 MINHAS METAS DE ECONOMIA                        │
├──────────────────────────────────────────────────────┤
│                                                      │
│  ┌────────────────────────────────────────────┐    │
│  │  📱 Notebook Gamer Dell G15                │    │
│  │  🟡 Importante                              │    │
│  │                                              │    │
│  │  ████████████░░░░░░░░░░ 60%                │    │
│  │  R$ 3.000 / R$ 5.000                        │    │
│  │  Faltam: R$ 2.000                           │    │
│  │                                              │    │
│  │  📊 Projeção: 4 meses (Junho/2026)          │    │
│  │  💡 Guardar R$ 833/mês para atingir meta    │    │
│  │                                              │    │
│  │  🔗 [Ver produto] [+ Depositar] [Editar]    │    │
│  └────────────────────────────────────────────┘    │
│                                                      │
│  ┌────────────────────────────────────────────┐    │
│  │  🏖️ Viagem para Cancún                     │    │
│  │  🟢 Desejo                                  │    │
│  │                                              │    │
│  │  ██████░░░░░░░░░░░░░░░░ 30%                │    │
│  │  R$ 2.400 / R$ 8.000                        │    │
│  │  Faltam: R$ 5.600                           │    │
│  │                                              │    │
│  │  📊 Projeção: 14 meses (Março/2027)         │    │
│  │  💡 Guardar R$ 400/mês para atingir meta    │    │
│  │                                              │    │
│  │  🔗 [Ver detalhes] [+ Depositar] [Editar]   │    │
│  └────────────────────────────────────────────┘    │
│                                                      │
│  ┌────────────────────────────────────────────┐    │
│  │  🎸 Guitarra Fender Stratocaster           │    │
│  │  🔴 Urgente                                 │    │
│  │                                              │    │
│  │  ██████████████████░░░░ 95%                │    │
│  │  R$ 2.850 / R$ 3.000                        │    │
│  │  Faltam apenas: R$ 150! 🎉                 │    │
│  │                                              │    │
│  │  📊 Você consegue comprar ESTE MÊS!         │    │
│  │  💡 Falta só mais R$ 150                    │    │
│  │                                              │    │
│  │  🔗 [Ver produto] [+ Depositar] [COMPRAR!]  │    │
│  └────────────────────────────────────────────┘    │
│                                                      │
│  Total em metas: R$ 8.250 / R$ 16.000 (52%)        │
│  [+ Nova Meta]                                       │
└──────────────────────────────────────────────────────┘
```

### Detalhes da Meta (Expandido)

```
┌────────────────────────────────────────────────────┐
│  🎯 Meta: Notebook Gamer Dell G15                 │
├────────────────────────────────────────────────────┤
│                                                    │
│  [Imagem do notebook Dell G15]                     │
│                                                    │
│  💰 Progresso Financeiro                           │
│  ████████████░░░░░░░░░░ 60%                      │
│  R$ 3.000,00 / R$ 5.000,00                        │
│                                                    │
│  📊 PROJEÇÕES INTELIGENTES                         │
│  ┌──────────────────────────────────────────┐    │
│  │  No ritmo atual de economia:              │    │
│  │  Média mensal: R$ 500/mês                 │    │
│  │                                            │    │
│  │  ⏰ Tempo estimado: 4 meses                │    │
│  │  📅 Data prevista: Junho/2026              │    │
│  │                                            │    │
│  │  💡 Para comprar ANTES (Abril):            │    │
│  │  Você precisa guardar R$ 1.000/mês         │    │
│  └──────────────────────────────────────────┘    │
│                                                    │
│  🛒 Informações do Produto                         │
│  Preço atual: R$ 5.000,00                         │
│  Última checagem: há 2 dias                        │
│  Link: dell.com/notebook-g15                       │
│  [🔗 Abrir Loja] [🔄 Atualizar Preço]            │
│                                                    │
│  📈 Histórico de Depósitos                         │
│  • 01/02: +R$ 500 (Poupança mensal)               │
│  • 15/01: +R$ 200 (Extra do freelance)            │
│  • 05/01: +R$ 300 (Bônus de fim de ano)           │
│  • 10/12: +R$ 500 (Poupança mensal)               │
│  ...                                               │
│                                                    │
│  [+ Depositar Agora] [Retirar] [Editar] [Excluir] │
└────────────────────────────────────────────────────┘
```

### Depósito em Meta

```
┌────────────────────────────────────────┐
│  💰 Depositar na Meta                 │
├────────────────────────────────────────┤
│  Meta: Notebook Gamer Dell G15        │
│  Progresso atual: R$ 3.000 / R$ 5.000 │
│                                        │
│  Valor a depositar:                    │
│  R$ [___________]                      │
│                                        │
│  Atalhos:                              │
│  [R$ 100] [R$ 250] [R$ 500] [R$ 1000] │
│                                        │
│  De onde vem o dinheiro?               │
│  ⚫ Poupança geral                     │
│  ⚪ Conta corrente                     │
│  ⚪ Extra (freelance, bônus)           │
│                                        │
│  Observação:                           │
│  [Extra do freelance deste mês_____]   │
│                                        │
│  [Cancelar]        [Depositar 💰]      │
└────────────────────────────────────────┘
```

### Sistema de Projeções

**Cálculo automático:**

```javascript
// Exemplo de lógica de projeção

Meta: R$ 5.000
Já economizado: R$ 3.000
Falta: R$ 2.000

// Analisa histórico de poupança
Últimos 3 meses: R$ 500, R$ 600, R$ 400
Média mensal: R$ 500

// Projeção padrão
Meses necessários = 2.000 / 500 = 4 meses
Data prevista = hoje + 4 meses = Junho/2026

// Projeção otimista (melhor mês)
Meses necessários = 2.000 / 600 = 3,3 meses ≈ 4 meses

// Projeção pessimista (pior mês)
Meses necessários = 2.000 / 400 = 5 meses

// Para atingir em prazo específico (ex: 2 meses)
Necessário por mês = 2.000 / 2 = R$ 1.000/mês
```

### Notificações de Progresso

**Alerta 25%:**
```
┌─────────────────────────────────────┐
│  🎉 Tony Save - Conquista!         │
├─────────────────────────────────────┤
│  Meta: Notebook Gamer              │
│                                     │
│  Você já economizou 25%! 🎯        │
│  R$ 1.250 / R$ 5.000                │
│                                     │
│  Continue assim! 💪                 │
└─────────────────────────────────────┘
```

**Alerta 50%:**
```
┌─────────────────────────────────────┐
│  🔥 Tony Save - Metade do caminho! │
├─────────────────────────────────────┤
│  Meta: Notebook Gamer              │
│                                     │
│  50% COMPLETO! 🎯🎯                │
│  R$ 2.500 / R$ 5.000                │
│                                     │
│  Falta só mais R$ 2.500!            │
│  Você está ARRASANDO! 🚀           │
└─────────────────────────────────────┘
```

**Alerta 100% (Meta atingida!):**
```
┌─────────────────────────────────────┐
│  🎊 PARABÉNS! META ATINGIDA! 🎊   │
├─────────────────────────────────────┤
│  Meta: Notebook Gamer Dell G15     │
│                                     │
│  💰 R$ 5.000 / R$ 5.000 ✅         │
│                                     │
│  Você conseguiu! 🎉                │
│  Tempo total: 8 meses               │
│                                     │
│  [Ver Produto] [Marcar como Comprado]│
└─────────────────────────────────────┘
```

**Alerta de mudança de preço:**
```
┌─────────────────────────────────────┐
│  💰 Tony Save - Alerta de Preço!   │
├─────────────────────────────────────┤
│  Meta: Notebook Gamer Dell G15     │
│                                     │
│  ⬇️ PREÇO CAIU!                    │
│  De: R$ 5.000,00                    │
│  Para: R$ 4.500,00 (-10%)           │
│                                     │
│  Você já tem R$ 3.000 economizados  │
│  Faltam apenas R$ 1.500 agora!      │
│                                     │
│  [Ver Oferta] [Atualizar Meta]      │
└─────────────────────────────────────┘
```

### Priorização e Sugestões

**Quando poupança mensal entra:**
```
┌────────────────────────────────────────┐
│  💰 Como alocar sua poupança?         │
├────────────────────────────────────────┤
│  Você economizou R$ 600 este mês!     │
│                                        │
│  Sugestões baseadas em suas metas:     │
│                                        │
│  🔴 Guitarra (95%) - QUASE LÁ!        │
│  Depositar: R$ 150 → COMPLETA! 🎉     │
│                                        │
│  🟡 Notebook (60%)                     │
│  Depositar: R$ 300                     │
│                                        │
│  🟢 Viagem (30%)                       │
│  Depositar: R$ 150                     │
│                                        │
│  Total: R$ 600                         │
│                                        │
│  [Aceitar Sugestão] [Customizar]       │
└────────────────────────────────────────┘
```

### Recursos Extras

**1. Comparação de Preços:**
- Sistema checa periodicamente o link do produto
- Alerta se preço subir ou cair
- Histórico de variação de preço

**2. Metas Compartilhadas:**
- Ex: Casal economizando juntos para viagem
- Ambos depositam e acompanham progresso

**3. Categorias de Metas:**
- 🏠 Casa (móveis, reforma)
- 🚗 Transporte (carro, moto)
- 📱 Tecnologia (notebook, celular)
- 🏖️ Viagem
- 📚 Educação (curso, faculdade)
- 💍 Eventos (casamento, festa)
- 💰 Investimento/Reserva

**4. Gamificação:**
- Badges/troféus ao completar metas
- Streak de depósitos mensais consecutivos
- Ranking de progresso (se múltiplas metas)

### Exemplos Práticos - Casos de Uso

**Exemplo 1: Economizar para PS5 em vez de parcelar**

**Situação:** Você quer um PS5 que custa R$ 4.500

```
┌────────────────────────────────────────────────────┐
│  🎮 Meta: PlayStation 5 + 2 Jogos                 │
├────────────────────────────────────────────────────┤
│                                                    │
│  💰 COMPARAÇÃO: À Vista vs Parcelado               │
│  ┌──────────────────────────────────────────┐    │
│  │  💳 No Cartão (12x sem juros):            │    │
│  │  12x de R$ 375 = R$ 4.500                 │    │
│  │  Você demora 12 meses pra pagar           │    │
│  │                                            │    │
│  │  💰 À Vista com desconto (10%):            │    │
│  │  R$ 4.050 (economia de R$ 450!)           │    │
│  │  Você guarda por 8 meses e compra         │    │
│  └──────────────────────────────────────────┘    │
│                                                    │
│  🎯 Sua Meta: R$ 4.050 à vista                    │
│  ████████████████░░░░ 80%                         │
│  R$ 3.240 / R$ 4.050                              │
│  Faltam: R$ 810                                    │
│                                                    │
│  📊 No ritmo atual (R$ 500/mês):                  │
│  ⏰ Faltam 2 meses!                               │
│  📅 Você compra em: Abril/2026                    │
│                                                    │
│  ✅ Vantagens de esperar:                         │
│  • Economiza R$ 450 (desconto à vista)            │
│  • Compra 4 meses ANTES (8 vs 12 meses)           │
│  • Não compromete limite do cartão                │
│  • Produto é seu de verdade (pago!)               │
│                                                    │
│  [+ Depositar] [Ver Produto] [Comprar!]           │
└────────────────────────────────────────────────────┘
```

**Exemplo 2: Entrada do Carro**

**Situação:** Quer dar R$ 15.000 de entrada num carro

```
┌────────────────────────────────────────────────────┐
│  🚗 Meta: Entrada do Carro (30%)                  │
├────────────────────────────────────────────────────┤
│  Carro: Fiat Argo 2024                            │
│  Valor total: R$ 50.000                            │
│  Entrada (30%): R$ 15.000                          │
│                                                    │
│  ██████████░░░░░░░░░░ 50%                         │
│  R$ 7.500 / R$ 15.000                             │
│  Faltam: R$ 7.500                                  │
│                                                    │
│  📊 Projeção (guardando R$ 800/mês):              │
│  ⏰ Faltam 9,4 meses ≈ 10 meses                   │
│  📅 Entrada pronta em: Novembro/2026              │
│                                                    │
│  💡 Quer dar entrada ANTES?                        │
│  Para Agosto/2026 (6 meses):                       │
│  Guardar R$ 1.250/mês                             │
│                                                    │
│  🎯 Benefícios de juntar entrada maior:            │
│  Entrada R$ 15k → Parcelas menores               │
│  Financiamento mais curto                          │
│  Menos juros totais                                │
│                                                    │
│  Histórico de depósitos:                           │
│  • 01/02: +R$ 800 (Poupança mensal)               │
│  • 15/01: +R$ 1.200 (13º salário)                 │
│  • 10/01: +R$ 800 (Poupança mensal)               │
│  ...                                               │
│                                                    │
│  [+ Depositar] [Simular Financiamento]             │
└────────────────────────────────────────────────────┘
```

**Exemplo 3: Notebook Gamer à vista**

**Situação:** Notebook de R$ 5.000 na loja

```
┌────────────────────────────────────────────────────┐
│  💻 Meta: Notebook Gamer Lenovo Legion            │
├────────────────────────────────────────────────────┤
│                                                    │
│  🏷️ ACOMPANHAMENTO DE PREÇO                       │
│  ┌──────────────────────────────────────────┐    │
│  │  Preço atual: R$ 5.000 (à vista)          │    │
│  │  Histórico:                                │    │
│  │  • 01/02: R$ 5.000 ✓                      │    │
│  │  • 15/01: R$ 5.200 📈                     │    │
│  │  • 01/01: R$ 4.800 📉 (melhor!)           │    │
│  │                                            │    │
│  │  💡 Preço está estável                     │    │
│  └──────────────────────────────────────────┘    │
│                                                    │
│  ████████████████████░ 95%                        │
│  R$ 4.750 / R$ 5.000                              │
│  Faltam apenas: R$ 250! 🎉                        │
│                                                    │
│  📊 Você consegue comprar ESTE MÊS!               │
│                                                    │
│  💰 ECONOMIA À VISTA:                              │
│  Parcelado: 10x R$ 530 = R$ 5.300 (juros)         │
│  À vista: R$ 5.000 (sem juros)                    │
│  Você economiza: R$ 300!                          │
│                                                    │
│  + Desconto adicional à vista: -10%               │
│  Preço final: R$ 4.500                            │
│  ECONOMIA TOTAL: R$ 800! 🎊                       │
│                                                    │
│  🔗 [Ver na Loja] [Negociar Desconto]             │
│  [+ Depositar R$ 250] [COMPRAR AGORA!]            │
└────────────────────────────────────────────────────┘
```

**Exemplo 4: Reforma da Casa**

```
┌────────────────────────────────────────────────────┐
│  🏠 Meta: Reforma da Cozinha                      │
├────────────────────────────────────────────────────┤
│  Orçamento total: R$ 12.000                        │
│  (Piso, azulejo, armários, bancada)                │
│                                                    │
│  ████████░░░░░░░░░░░░ 40%                         │
│  R$ 4.800 / R$ 12.000                             │
│  Faltam: R$ 7.200                                  │
│                                                    │
│  📊 Projeção (R$ 600/mês):                        │
│  ⏰ 12 meses                                       │
│  📅 Reforma pronta em: Fevereiro/2027             │
│                                                    │
│  💡 Fazer em etapas:                               │
│  Etapa 1: Piso (R$ 3.000) - ✅ PODE FAZER!        │
│  Etapa 2: Azulejo (R$ 2.500) - 4 meses            │
│  Etapa 3: Armários (R$ 6.500) - 10 meses          │
│                                                    │
│  🎯 Vantagem de pagar à vista ao fornecedor:       │
│  Desconto médio: 15% em material                   │
│  Economia estimada: R$ 1.800                      │
│                                                    │
│  [+ Depositar] [Solicitar Orçamento]               │
└────────────────────────────────────────────────────┘
```

**Exemplo 5: Viagem para o Exterior**

```
┌────────────────────────────────────────────────────┐
│  ✈️ Meta: Viagem para Disney (Orlando)            │
├────────────────────────────────────────────────────┤
│  Orçamento: R$ 18.000 (casal, 10 dias)             │
│  Passagens: R$ 6.000                               │
│  Hotel: R$ 5.000                                   │
│  Ingressos: R$ 3.000                               │
│  Alimentação/extras: R$ 4.000                      │
│                                                    │
│  ██████████████░░░░░░ 70%                         │
│  R$ 12.600 / R$ 18.000                            │
│  Faltam: R$ 5.400                                  │
│                                                    │
│  📊 Projeção (R$ 900/mês):                        │
│  ⏰ 6 meses                                        │
│  📅 Viagem prevista: Agosto/2026                  │
│                                                    │
│  🎯 Data alvo: Julho/2026 (férias)                │
│  Para viajar em Julho, guardar: R$ 1.350/mês      │
│                                                    │
│  💰 Vantagem de pagar antecipado:                  │
│  • Passagens mais baratas (6 meses antes)         │
│  • Hotéis com desconto (reserva antecipada)       │
│  • Sem estresse de pagar voltando                 │
│  Economia estimada: R$ 2.500                      │
│                                                    │
│  [+ Depositar] [Pesquisar Passagens]               │
└────────────────────────────────────────────────────┘
```

### Calculadora de Vantagem À Vista

**Recurso automático:**
```
┌────────────────────────────────────────┐
│  💰 VALE A PENA ESPERAR?              │
├────────────────────────────────────────┤
│  Produto: PS5                         │
│  Preço: R$ 4.500                      │
│                                        │
│  📊 COMPARAÇÃO:                        │
│                                        │
│  Opção 1: Comprar Parcelado HOJE      │
│  12x R$ 412,50 = R$ 4.950 (10% juros) │
│  Você tem agora ✓                     │
│  Gasta total: R$ 4.950                │
│                                        │
│  Opção 2: Economizar e Comprar À Vista│
│  Guardar R$ 562,50/mês por 8 meses    │
│  Você tem em: Outubro/2026            │
│  À vista com 10% desconto: R$ 4.050   │
│  Gasta total: R$ 4.050                │
│                                        │
│  🎯 RESULTADO:                         │
│  Economiza: R$ 900!                   │
│  Tem 4 meses antes!                   │
│                                        │
│  💡 Recomendação: ESPERAR              │
│  Vale muito a pena!                    │
└────────────────────────────────────────┘
```

---

## Sistema de Contas e Carteiras - Detalhamento

### Como Funciona o Saldo Calculado

O sistema mantém uma "foto" atualizada do saldo de cada conta através do registro de transações:

```
EXEMPLO PRÁTICO:

1. Você cria a conta:
   Conta Corrente Nubank
   Saldo inicial: R$ 1.500,00
   (O que você tem na conta HOJE)

2. Você registra transações vinculadas a essa conta:

   05/Fev - Salário recebido       +R$ 3.000,00  → Saldo: R$ 4.500,00
   08/Fev - Aluguel pago            -R$ 1.200,00  → Saldo: R$ 3.300,00
   10/Fev - Compra mercado          -R$ 350,00    → Saldo: R$ 2.950,00
   12/Fev - Freelance recebido      +R$ 800,00    → Saldo: R$ 3.750,00
   15/Fev - Conta de luz            -R$ 150,00    → Saldo: R$ 3.600,00

3. O sistema calcula automaticamente:
   Saldo atual da Conta Nubank: R$ 3.600,00

   (Saldo inicial + receitas - despesas = saldo atual)
```

### Dashboard de Contas

```
┌──────────────────────────────────────────────────────┐
│  💰 MINHAS CONTAS E SALDO DISPONÍVEL                │
├──────────────────────────────────────────────────────┤
│                                                      │
│  🏦 Conta Corrente Nubank                           │
│  Saldo: R$ 3.600,00                                 │
│  Última movimentação: há 2 dias                      │
│  [Ver Extrato] [Nova Transação]                      │
│                                                      │
│  💰 Poupança Nubank                                 │
│  Saldo: R$ 8.450,00                                 │
│  Última movimentação: há 15 dias                     │
│  [Ver Extrato] [Nova Transação]                      │
│                                                      │
│  💳 PicPay                                          │
│  Saldo: R$ 245,80                                   │
│  Última movimentação: ontem                          │
│  [Ver Extrato] [Nova Transação]                      │
│                                                      │
│  💵 Dinheiro Físico (Carteira)                      │
│  Saldo: R$ 120,00                                   │
│  Última movimentação: há 3 dias                      │
│  [Ver Extrato] [Nova Transação]                      │
│                                                      │
│  ──────────────────────────────────────────────      │
│  SALDO TOTAL DISPONÍVEL: R$ 12.415,80               │
│  [+ Adicionar Conta] [Transferir entre Contas]       │
└──────────────────────────────────────────────────────┘
```

### Cadastro de Nova Conta

```
┌────────────────────────────────────────────┐
│  💰 Adicionar Nova Conta                  │
├────────────────────────────────────────────┤
│                                            │
│  Tipo de conta:                            │
│  ⚫ Conta Corrente                         │
│  ⚪ Poupança                                │
│  ⚪ Carteira Digital                        │
│  ⚪ Dinheiro Físico                         │
│  ⚪ Outra                                   │
│                                            │
│  Nome/Banco:                               │
│  [Nubank_____________________]             │
│                                            │
│  Saldo inicial (quanto tem agora):         │
│  R$ [1.500,00]                             │
│                                            │
│  💡 A partir de agora, todas as            │
│  transações vão atualizar esse saldo       │
│  automaticamente                            │
│                                            │
│  Cor (para visualização):                  │
│  🟣 🔴 🔵 🟢 🟡 ⚫                          │
│                                            │
│  Observações:                              │
│  [Conta principal para receber salário]    │
│                                            │
│  [Cancelar]        [Criar Conta]           │
└────────────────────────────────────────────┘
```

### Registro de Transação com Conta

```
┌────────────────────────────────────────────┐
│  💸 Nova Transação                        │
├────────────────────────────────────────────┤
│  Tipo:                                     │
│  ⚫ Despesa  ⚪ Receita                    │
│                                            │
│  Valor:                                    │
│  R$ [350,00]                               │
│                                            │
│  Descrição:                                │
│  [Compra no Mercado Extra_________]        │
│                                            │
│  Categoria:                                │
│  [Alimentação ▼]                           │
│                                            │
│  🏦 Conta de origem/destino:               │
│  ⚫ Conta Corrente Nubank (R$ 3.600)       │
│  ⚪ Poupança Nubank (R$ 8.450)             │
│  ⚪ PicPay (R$ 245,80)                     │
│  ⚪ Dinheiro Físico (R$ 120)               │
│                                            │
│  💡 Novo saldo após transação:             │
│  Conta Nubank: R$ 3.250,00                 │
│  (R$ 3.600 - R$ 350)                       │
│                                            │
│  Data:                                     │
│  [05/02/2026 📅]                          │
│                                            │
│  [Cancelar]        [Registrar]             │
└────────────────────────────────────────────┘
```

### Transferência Entre Contas

```
┌────────────────────────────────────────────┐
│  🔄 Transferência Entre Contas            │
├────────────────────────────────────────────┤
│  Valor:                                    │
│  R$ [500,00]                               │
│                                            │
│  De (origem):                              │
│  [Conta Corrente Nubank ▼]                 │
│  Saldo atual: R$ 3.600,00                  │
│  Novo saldo: R$ 3.100,00                   │
│                                            │
│  Para (destino):                           │
│  [Poupança Nubank ▼]                       │
│  Saldo atual: R$ 8.450,00                  │
│  Novo saldo: R$ 8.950,00                   │
│                                            │
│  Data:                                     │
│  [05/02/2026 📅]                          │
│                                            │
│  Observação:                               │
│  [Guardar para reserva de emergência___]   │
│                                            │
│  💡 Saldo total permanece igual            │
│  (R$ 12.050 → R$ 12.050)                   │
│                                            │
│  [Cancelar]        [Transferir]            │
└────────────────────────────────────────────┘
```

### Extrato Detalhado da Conta

```
┌────────────────────────────────────────────────────────┐
│  💰 Extrato - Conta Corrente Nubank                   │
├────────────────────────────────────────────────────────┤
│  Saldo atual: R$ 3.600,00                             │
│  Período: Fevereiro/2026                               │
│                                                        │
│  ┌────────────────────────────────────────────────┐  │
│  │  01/Fev - Saldo inicial            R$ 1.500,00 │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  05/Fev 🟢 Salário recebido                           │
│  +R$ 3.000,00                    Saldo: R$ 4.500,00   │
│  Receita • Trabalho                                   │
│                                                        │
│  08/Fev 🔴 Aluguel                                    │
│  -R$ 1.200,00                    Saldo: R$ 3.300,00   │
│  Despesa • Moradia                                    │
│                                                        │
│  10/Fev 🔴 Mercado Extra                              │
│  -R$ 350,00                      Saldo: R$ 2.950,00   │
│  Despesa • Alimentação                                │
│                                                        │
│  12/Fev 🟢 Freelance DevXYZ                           │
│  +R$ 800,00                      Saldo: R$ 3.750,00   │
│  Receita • Trabalho                                   │
│                                                        │
│  15/Fev 🔴 Conta de Luz                               │
│  -R$ 150,00                      Saldo: R$ 3.600,00   │
│  Despesa • Moradia                                    │
│                                                        │
│  ──────────────────────────────────────────────        │
│  Resumo do Período:                                   │
│  Receitas: +R$ 3.800,00                               │
│  Despesas: -R$ 1.700,00                               │
│  Saldo Final: R$ 3.600,00                             │
│                                                        │
│  [Exportar PDF] [Filtrar Categoria]                   │
└────────────────────────────────────────────────────────┘
```

### Conciliação Bancária

```
┌────────────────────────────────────────────┐
│  🔍 Conciliação Bancária                  │
├────────────────────────────────────────────┤
│  Conta: Conta Corrente Nubank             │
│                                            │
│  💰 Saldo no App:                          │
│  R$ 3.600,00                               │
│  (Calculado pelas suas transações)         │
│                                            │
│  🏦 Saldo Real no Banco:                   │
│  R$ [_______]                              │
│  (Digite o saldo que aparece no app/banco) │
│                                            │
│  ──────────────────────────────────        │
│                                            │
│  🟢 Saldos conferem!                       │
│  Tudo certo, seu controle está preciso     │
│                                            │
│  [OK]                                      │
└────────────────────────────────────────────┘
```

**Se houver diferença:**
```
┌────────────────────────────────────────────┐
│  ⚠️ Diferença Encontrada                  │
├────────────────────────────────────────────┤
│  Saldo no App: R$ 3.600,00                 │
│  Saldo Real: R$ 3.450,00                   │
│                                            │
│  Diferença: -R$ 150,00                     │
│                                            │
│  Possíveis causas:                         │
│  • Transação não registrada no app         │
│  • Taxa bancária não lançada               │
│  • Compra que você esqueceu                │
│                                            │
│  💡 Revise seu extrato bancário e          │
│  registre transações faltantes             │
│                                            │
│  [Ajustar Saldo] [Revisar Extrato]         │
└────────────────────────────────────────────┘
```

### Integração com Captura Automática

```
Quando notificação é capturada:
"Nubank: Compra aprovada R$ 85,00 - POSTO SHELL"

Sistema automaticamente:
1. Identifica a conta: Conta Corrente Nubank
2. Cria transação de despesa: -R$ 85,00
3. Atualiza saldo: R$ 3.600 → R$ 3.515
4. Pede categorização ao usuário
5. Sincroniza em tempo real

┌────────────────────────────────────────────┐
│  🔔 Nova Transação Detectada              │
├────────────────────────────────────────────┤
│  Conta: Conta Corrente Nubank             │
│  Valor: -R$ 85,00                          │
│  Local: POSTO SHELL                        │
│                                            │
│  Saldo antes: R$ 3.600,00                  │
│  Saldo depois: R$ 3.515,00                 │
│                                            │
│  Categorizar como:                         │
│  [🚗 Transporte] [🍔 Alimentação]         │
│                                            │
│  [Confirmar]                               │
└────────────────────────────────────────────┘
```

### Visão Geral - Todas as Contas

```
┌────────────────────────────────────────────────────────┐
│  📊 VISÃO GERAL DAS CONTAS                            │
├────────────────────────────────────────────────────────┤
│                                                        │
│  Total Disponível: R$ 12.415,80                       │
│                                                        │
│  Distribuição:                                         │
│  ████████████████████████████ Poupança (68%) R$ 8.450 │
│  ███████████░░░░░░░░░░░░░░░░░ C.Corrente (29%) R$ 3.6k│
│  ██░░░░░░░░░░░░░░░░░░░░░░░░░░ PicPay (2%) R$ 245      │
│  █░░░░░░░░░░░░░░░░░░░░░░░░░░░ Dinheiro (1%) R$ 120    │
│                                                        │
│  Evolução (últimos 3 meses):                           │
│  Dez: R$ 10.200                                       │
│  Jan: R$ 11.800                                       │
│  Fev: R$ 12.416  📈 +21% em 3 meses                   │
│                                                        │
│  💡 Você está guardando bem! Continue assim           │
│                                                        │
│  [Ver Detalhes] [Transferir] [Nova Transação]         │
└────────────────────────────────────────────────────────┘
```

---

## Sistema de Transações Recorrentes - Detalhamento

### Cadastro de Receita Recorrente

```
┌────────────────────────────────────────────────────────┐
│  💰 Nova Receita Recorrente                           │
├────────────────────────────────────────────────────────┤
│                                                        │
│  Tipo de receita:                                      │
│  ⚫ 💼 Salário                                         │
│  ⚪ 🏢 Freelance fixo                                  │
│  ⚪ 🏠 Aluguel recebido                                │
│  ⚪ 💵 Pensão/benefício                                │
│  ⚪ 📈 Dividendos/investimentos                        │
│  ⚪ 💰 Outra                                           │
│                                                        │
│  Descrição:                                            │
│  [Salário - Empresa XYZ___________________]            │
│                                                        │
│  Valor (aproximado):                                   │
│  R$ [3.000,00]                                         │
│  ☑️ Permitir ajuste ao lançar                         │
│                                                        │
│  Conta de destino:                                     │
│  [Conta Corrente Nubank ▼]                            │
│                                                        │
│  Categoria:                                            │
│  [Salário ▼]                                           │
│                                                        │
│  ─── REGRAS DE REPETIÇÃO ────                          │
│                                                        │
│  Frequência:                                           │
│  ⚫ Mensal  ⚪ Semanal  ⚪ Quinzenal  ⚪ Trimestral     │
│                                                        │
│  Quando recebe? (escolha uma opção):                   │
│                                                        │
│  ⚫ Todo dia fixo do mês:                              │
│     Dia [5 ▼] de cada mês                             │
│                                                        │
│  ⚪ Todo Xº dia útil do mês:                           │
│     [5º ▼] dia útil                                    │
│     💡 Pula finais de semana e feriados                │
│                                                        │
│  ⚪ Toda Xª semana do mês:                             │
│     [1ª ▼] [Segunda ▼] do mês                         │
│     Ex: 1ª segunda-feira, 2ª sexta-feira              │
│                                                        │
│  ⚪ Último dia do mês                                  │
│                                                        │
│  ⚪ Último dia útil do mês                             │
│                                                        │
│  ⚪ A cada X dias:                                     │
│     A cada [30 ▼] dias                                 │
│                                                        │
│  ─────────────────────────────                         │
│                                                        │
│  Próximo lançamento previsto:                          │
│  📅 05/Março/2026 (Quarta-feira)                      │
│                                                        │
│  Data de início:                                       │
│  [01/01/2024 📅]                                      │
│                                                        │
│  Data de término (opcional):                           │
│  ⚫ Indeterminado                                      │
│  ⚪ Até [_________ 📅]                                │
│                                                        │
│  Lançamento automático:                                │
│  ⚫ Lançar automaticamente (com confirmação)           │
│  ⚪ Apenas notificar (lançamento manual)               │
│                                                        │
│  Observações:                                          │
│  [_________________________________________]           │
│                                                        │
│  [Cancelar]           [Criar Recorrência 💰]           │
└────────────────────────────────────────────────────────┘
```

### Cadastro de Despesa Recorrente

```
┌────────────────────────────────────────────────────────┐
│  💸 Nova Despesa Recorrente                           │
├────────────────────────────────────────────────────────┤
│                                                        │
│  Tipo de despesa:                                      │
│  ⚫ 🏠 Aluguel/Moradia                                 │
│  ⚪ 💡 Conta (água, luz, internet)                     │
│  ⚪ 🏥 Plano de saúde                                  │
│  ⚪ 🎓 Mensalidade (escola, curso)                     │
│  ⚪ 🚗 Seguro                                          │
│  ⚪ 💳 Outra                                           │
│                                                        │
│  Descrição:                                            │
│  [Aluguel - Apartamento Centro_________]               │
│                                                        │
│  Valor (aproximado):                                   │
│  R$ [1.200,00]                                         │
│  ☑️ Permitir ajuste ao lançar                         │
│  (útil para contas que variam, como água/luz)          │
│                                                        │
│  Conta de origem:                                      │
│  [Conta Corrente Nubank ▼]                            │
│                                                        │
│  Categoria:                                            │
│  [Moradia ▼]                                           │
│                                                        │
│  ─── REGRAS DE REPETIÇÃO ────                          │
│                                                        │
│  Vencimento:                                           │
│  ⚫ Todo dia [10 ▼] do mês                             │
│                                                        │
│  Próximo lançamento previsto:                          │
│  📅 10/Março/2026 (Terça-feira)                       │
│                                                        │
│  Alertas:                                              │
│  ☑️ Notificar [3 ▼] dias antes do vencimento          │
│  ☑️ Notificar no dia do vencimento                     │
│                                                        │
│  Lançamento automático:                                │
│  ⚫ Lançar automaticamente (com confirmação)           │
│  ⚪ Apenas notificar (lançamento manual)               │
│                                                        │
│  [Cancelar]           [Criar Recorrência 💸]           │
└────────────────────────────────────────────────────────┘
```

### Dashboard de Recorrências

```
┌────────────────────────────────────────────────────────┐
│  🔄 MINHAS TRANSAÇÕES RECORRENTES                     │
├────────────────────────────────────────────────────────┤
│                                                        │
│  💰 RECEITAS RECORRENTES                              │
│  ┌────────────────────────────────────────────────┐  │
│  │  💼 Salário - Empresa XYZ                      │  │
│  │  R$ 3.000,00 • Todo dia 5                      │  │
│  │  Próximo: 📅 05/Mar (em 3 dias)                │  │
│  │  Conta: Nubank                                  │  │
│  │  Status: ✅ Ativo                              │  │
│  │  [Ver Histórico] [Editar] [Pausar]             │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  ┌────────────────────────────────────────────────┐  │
│  │  🏢 Freelance - Cliente ABC                    │  │
│  │  R$ 800,00 • 1º dia útil do mês                │  │
│  │  Próximo: 📅 01/Mar (em 1 dia)                 │  │
│  │  Conta: Nubank                                  │  │
│  │  Status: ✅ Ativo                              │  │
│  │  [Ver Histórico] [Editar] [Pausar]             │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  Total Receitas Mensais: R$ 3.800,00                  │
│                                                        │
│  💸 DESPESAS RECORRENTES                              │
│  ┌────────────────────────────────────────────────┐  │
│  │  🏠 Aluguel - Apartamento                      │  │
│  │  R$ 1.200,00 • Todo dia 10                     │  │
│  │  Próximo: 📅 10/Mar (em 8 dias)                │  │
│  │  Conta: Nubank                                  │  │
│  │  Status: ⚠️ Vencendo em breve                  │  │
│  │  [Ver Histórico] [Editar] [Pausar]             │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  ┌────────────────────────────────────────────────┐  │
│  │  💡 Conta de Luz - Energisa                    │  │
│  │  R$ ~150,00 • Todo dia 15                      │  │
│  │  Próximo: 📅 15/Mar (em 13 dias)               │  │
│  │  Conta: Nubank                                  │  │
│  │  Status: ✅ Ativo                              │  │
│  │  💡 Valor aproximado (varia mensalmente)        │  │
│  │  [Ver Histórico] [Editar] [Pausar]             │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  ┌────────────────────────────────────────────────┐  │
│  │  📱 Internet - Vivo Fibra                      │  │
│  │  R$ 99,90 • Todo dia 20                        │  │
│  │  Próximo: 📅 20/Mar (em 18 dias)               │  │
│  │  Conta: Nubank                                  │  │
│  │  Status: ✅ Ativo                              │  │
│  │  [Ver Histórico] [Editar] [Pausar]             │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  Total Despesas Mensais: R$ ~1.449,90                 │
│                                                        │
│  ──────────────────────────────────────────────        │
│  BALANÇO MENSAL RECORRENTE:                           │
│  Receitas: +R$ 3.800,00                               │
│  Despesas: -R$ 1.449,90                               │
│  Sobra garantida: R$ 2.350,10                         │
│  ──────────────────────────────────────────────        │
│                                                        │
│  [+ Nova Receita] [+ Nova Despesa]                     │
└────────────────────────────────────────────────────────┘
```

### Detecção Automática de Padrões

**Sistema analisa e sugere:**
```
┌────────────────────────────────────────────┐
│  🤖 Padrão Detectado!                     │
├────────────────────────────────────────────┤
│  Notamos que você recebe:                  │
│                                            │
│  💰 R$ 3.000,00                            │
│  📅 Todo dia 5 do mês                      │
│  🏦 Conta Corrente Nubank                  │
│  📝 Descrição: "Salário"                   │
│                                            │
│  Últimas entradas:                         │
│  • 05/Fev/2026: R$ 3.000,00 ✓             │
│  • 05/Jan/2026: R$ 3.000,00 ✓             │
│  • 05/Dez/2025: R$ 3.000,00 ✓             │
│  • 05/Nov/2025: R$ 3.000,00 ✓             │
│                                            │
│  💡 Quer criar uma receita recorrente?     │
│  Assim você pode:                          │
│  • Ver quando vai cair o próximo salário   │
│  • Projetar saldo futuro                   │
│  • Lançamento automático                   │
│                                            │
│  [Criar Recorrência] [Não, Obrigado]       │
└────────────────────────────────────────────┘
```

### Lançamento Automático com Confirmação

**Quando chega o dia previsto:**
```
┌────────────────────────────────────────────┐
│  💰 Lançamento Automático Pendente        │
├────────────────────────────────────────────┤
│  Receita: Salário - Empresa XYZ           │
│  Previsto para: Hoje (05/Mar)              │
│                                            │
│  Valor padrão: R$ 3.000,00                 │
│  Ajustar para: R$ [3.000,00]               │
│                                            │
│  Conta: Conta Corrente Nubank             │
│  Categoria: Salário                        │
│                                            │
│  Saldo antes: R$ 1.500,00                  │
│  Saldo depois: R$ 4.500,00                 │
│                                            │
│  [Cancelar] [Adiar] [Confirmar Lançamento] │
└────────────────────────────────────────────┘
```

**Para despesas que variam (ex: conta de luz):**
```
┌────────────────────────────────────────────┐
│  💡 Lançamento de Conta de Luz            │
├────────────────────────────────────────────┤
│  Despesa: Conta de Luz - Energisa         │
│  Vencimento: Hoje (15/Mar)                 │
│                                            │
│  Valor estimado: R$ 150,00                 │
│  Últimos meses:                            │
│  • Fev: R$ 145,80                          │
│  • Jan: R$ 168,50                          │
│  • Dez: R$ 142,30                          │
│  Média: R$ 152,20                          │
│                                            │
│  💡 Valor real deste mês:                  │
│  R$ [______]                               │
│                                            │
│  Conta: Conta Corrente Nubank             │
│                                            │
│  [Cancelar] [Adiar] [Confirmar]            │
└────────────────────────────────────────────┘
```

### Calendário de Fluxo de Caixa

```
┌────────────────────────────────────────────────────────┐
│  📅 CALENDÁRIO FINANCEIRO - Março/2026                │
├────────────────────────────────────────────────────────┤
│                                                        │
│  Dom  Seg  Ter  Qua  Qui  Sex  Sáb                    │
│   1    2    3    4    5    6    7                     │
│  🟢              🟢                                     │
│  R$800          R$3k                                   │
│                                                        │
│   8    9   10   11   12   13   14                     │
│             🔴                                          │
│           R$1.2k                                       │
│                                                        │
│  15   16   17   18   19   20   21                     │
│  🔴                     🔴                              │
│  R$150                 R$100                           │
│                                                        │
│  22   23   24   25   26   27   28                     │
│                                                        │
│                                                        │
│  29   30   31                                          │
│                                                        │
│                                                        │
│  ──────────────────────────────────────────────        │
│  Legenda:                                              │
│  🟢 Receita recorrente                                 │
│  🔴 Despesa recorrente                                 │
│                                                        │
│  Resumo do Mês:                                        │
│  Receitas previstas: +R$ 3.800,00                      │
│  Despesas previstas: -R$ 1.449,90                      │
│  Saldo esperado: +R$ 2.350,10                          │
│                                                        │
│  [◀ Fev] [Hoje] [Abr ▶]                               │
└────────────────────────────────────────────────────────┘
```

### Projeção de Saldo Futuro

```
┌────────────────────────────────────────────────────────┐
│  🔮 PROJEÇÃO DE SALDO - Próximos 3 Meses             │
├────────────────────────────────────────────────────────┤
│  Saldo atual: R$ 3.600,00                             │
│                                                        │
│  📊 Baseado em receitas/despesas recorrentes:          │
│                                                        │
│  ┌────────────────────────────────────────────────┐  │
│  │  📅 MARÇO/2026                                 │  │
│  ├────────────────────────────────────────────────┤  │
│  │  Saldo inicial:        R$ 3.600,00            │  │
│  │  + Receitas fixas:     R$ 3.800,00            │  │
│  │  - Despesas fixas:     R$ 1.449,90            │  │
│  │  - Gastos variáveis*:  R$ 1.100,00            │  │
│  │  ──────────────────────────────────────        │  │
│  │  Saldo final previsto: R$ 4.850,10            │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  ┌────────────────────────────────────────────────┐  │
│  │  📅 ABRIL/2026                                 │  │
│  ├────────────────────────────────────────────────┤  │
│  │  Saldo inicial:        R$ 4.850,10            │  │
│  │  + Receitas fixas:     R$ 3.800,00            │  │
│  │  - Despesas fixas:     R$ 1.449,90            │  │
│  │  - Gastos variáveis*:  R$ 1.100,00            │  │
│  │  ──────────────────────────────────────        │  │
│  │  Saldo final previsto: R$ 6.100,20            │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  ┌────────────────────────────────────────────────┐  │
│  │  📅 MAIO/2026                                  │  │
│  ├────────────────────────────────────────────────┤  │
│  │  Saldo inicial:        R$ 6.100,20            │  │
│  │  + Receitas fixas:     R$ 3.800,00            │  │
│  │  - Despesas fixas:     R$ 1.449,90            │  │
│  │  - Gastos variáveis*:  R$ 1.100,00            │  │
│  │  ──────────────────────────────────────        │  │
│  │  Saldo final previsto: R$ 7.350,30            │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  * Gastos variáveis baseados na média dos últimos 3m  │
│                                                        │
│  💡 Tendência: 📈 Poupando ~R$ 2.200/mês              │
│  Continue assim e terá R$ 7.350 em 3 meses!           │
└────────────────────────────────────────────────────────┘
```

### Histórico de Lançamentos da Recorrência

```
┌────────────────────────────────────────────────────────┐
│  📜 Histórico - Salário - Empresa XYZ                 │
├────────────────────────────────────────────────────────┤
│  Criado em: 01/Jan/2024                               │
│  Frequência: Mensal (dia 5)                            │
│  Status: ✅ Ativo                                     │
│                                                        │
│  Lançamentos (últimos 6 meses):                        │
│                                                        │
│  ✅ 05/Fev/2026 - R$ 3.000,00 (Confirmado)            │
│  ✅ 05/Jan/2026 - R$ 3.000,00 (Confirmado)            │
│  ✅ 05/Dez/2025 - R$ 3.200,00 (Ajustado - 13º)        │
│  ✅ 05/Nov/2025 - R$ 3.000,00 (Confirmado)            │
│  ✅ 05/Out/2025 - R$ 3.000,00 (Confirmado)            │
│  ✅ 05/Set/2025 - R$ 3.000,00 (Confirmado)            │
│                                                        │
│  Estatísticas:                                         │
│  Total recebido: R$ 72.000,00 (24 meses)              │
│  Média mensal: R$ 3.000,00                            │
│  Valor mais alto: R$ 3.200,00 (Dez/2025)              │
│  Taxa de confirmação: 100% (24/24)                     │
│                                                        │
│  Próximos lançamentos previstos:                       │
│  📅 05/Mar/2026 - R$ 3.000,00                         │
│  📅 05/Abr/2026 - R$ 3.000,00                         │
│  📅 05/Mai/2026 - R$ 3.000,00                         │
│                                                        │
│  [Editar Recorrência] [Pausar] [Excluir]              │
└────────────────────────────────────────────────────────┘
```

### Alerta de Mês Apertado

```
┌────────────────────────────────────────────┐
│  ⚠️ Atenção - Mês Apertado Previsto      │
├────────────────────────────────────────────┤
│  Mês: Abril/2026                           │
│                                            │
│  Receitas previstas:   R$ 3.800,00         │
│  Despesas previstas:   R$ 4.200,00         │
│  ────────────────────────────────           │
│  Déficit esperado:    -R$ 400,00 🔴        │
│                                            │
│  💡 Motivo:                                │
│  • IPVA do carro: R$ 800,00 (dia 15)      │
│                                            │
│  Sugestões:                                │
│  ✓ Guardar R$ 400 a mais este mês          │
│  ✓ Reduzir gastos variáveis em Abril       │
│  ✓ Buscar receita extra (freelance)        │
│                                            │
│  [Ver Detalhes] [Criar Meta de Poupança]   │
└────────────────────────────────────────────┘
```

### Notificação de Lançamento Próximo

```
┌─────────────────────────────────────┐
│  🔔 Tony Save - Receita Próxima   │
├─────────────────────────────────────┤
│  💰 Salário - Empresa XYZ          │
│                                     │
│  Cai amanhã! (05/Mar)               │
│  Valor: R$ 3.000,00                 │
│                                     │
│  Seu saldo vai subir de             │
│  R$ 1.500 → R$ 4.500 💚            │
│                                     │
│  [OK] [Ver Projeção do Mês]         │
└─────────────────────────────────────┘
```

---

## Sistema de Cartões de Crédito - Detalhamento

### Dashboard de Cartões

```
┌──────────────────────────────────────────────────────┐
│  💳 MEUS CARTÕES DE CRÉDITO                         │
├──────────────────────────────────────────────────────┤
│                                                      │
│  ┌────────────────────────────────────────────┐    │
│  │  💳 Nubank Ultravioleta                    │    │
│  │  **** **** **** 1234                       │    │
│  │                                              │    │
│  │  Fatura Atual (Fev/2026):                   │    │
│  │  R$ 2.847,90                                │    │
│  │  ██████████████░░░░░ 71% do limite         │    │
│  │                                              │    │
│  │  Limite: R$ 4.000,00                        │    │
│  │  Disponível: R$ 1.152,10                    │    │
│  │                                              │    │
│  │  Fechamento: 15/Fev • Vencimento: 22/Fev    │    │
│  │                                              │    │
│  │  [Ver Fatura Detalhada]                     │    │
│  └────────────────────────────────────────────┘    │
│                                                      │
│  ┌────────────────────────────────────────────┐    │
│  │  💳 Inter Mastercard Black                 │    │
│  │  **** **** **** 5678                       │    │
│  │                                              │    │
│  │  Fatura Atual (Fev/2026):                   │    │
│  │  R$ 1.245,00                                │    │
│  │  ████████░░░░░░░░░░░ 41% do limite         │    │
│  │                                              │    │
│  │  Limite: R$ 3.000,00                        │    │
│  │  Disponível: R$ 1.755,00                    │    │
│  │                                              │    │
│  │  Fechamento: 10/Fev • Vencimento: 17/Fev    │    │
│  │                                              │    │
│  │  [Ver Fatura Detalhada]                     │    │
│  └────────────────────────────────────────────┘    │
│                                                      │
│  Total em faturas: R$ 4.092,90                      │
│  [+ Adicionar Novo Cartão]                           │
└──────────────────────────────────────────────────────┘
```

### Fatura Detalhada - Com Separação de Tipos

```
┌────────────────────────────────────────────────────────┐
│  💳 Nubank Ultravioleta - Fatura Fevereiro/2026       │
├────────────────────────────────────────────────────────┤
│                                                        │
│  Status: 🟢 Aberta                                    │
│  Fechamento: 15/Fev • Vencimento: 22/Fev              │
│                                                        │
│  ──────────────────────────────────────────────        │
│  TOTAL DA FATURA: R$ 2.847,90                         │
│  ──────────────────────────────────────────────        │
│                                                        │
│  ┌────────────────────────────────────────────────┐  │
│  │  🛒 GASTOS ATIVOS/PONTUAIS (Este mês)         │  │
│  │  R$ 1.247,90                                   │  │
│  ├────────────────────────────────────────────────┤  │
│  │  • 05/Fev - Mercado Extra      R$ 347,90      │  │
│  │  • 08/Fev - Posto Shell         R$ 250,00      │  │
│  │  • 10/Fev - iFood               R$ 85,00       │  │
│  │  • 12/Fev - Farmácia São Paulo  R$ 120,00      │  │
│  │  • 14/Fev - Amazon              R$ 445,00      │  │
│  │                                                 │  │
│  │  💡 Esses gastos variam todo mês               │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  ┌────────────────────────────────────────────────┐  │
│  │  🔄 GASTOS RECORRENTES/FIXOS                  │  │
│  │  R$ 250,00                                     │  │
│  ├────────────────────────────────────────────────┤  │
│  │  • 01/Fev - Netflix Premium     R$ 55,90       │  │
│  │              (Renovação automática)            │  │
│  │                                                 │  │
│  │  • 05/Fev - Spotify Family      R$ 34,90       │  │
│  │              (Renovação automática)            │  │
│  │                                                 │  │
│  │  • 10/Fev - Academia SmartFit   R$ 89,90       │  │
│  │              (Mensalidade)                      │  │
│  │                                                 │  │
│  │  • 15/Fev - Amazon Prime        R$ 14,90       │  │
│  │              (Assinatura mensal)               │  │
│  │                                                 │  │
│  │  • 20/Fev - iCloud 200GB        R$ 14,90       │  │
│  │              (Armazenamento)                    │  │
│  │                                                 │  │
│  │  • 25/Fev - Xbox Game Pass      R$ 39,50       │  │
│  │              (Assinatura mensal)               │  │
│  │                                                 │  │
│  │  💡 Esses gastos se repetem todo mês           │  │
│  │  📊 Previsão próximo mês: R$ 250,00            │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  ┌────────────────────────────────────────────────┐  │
│  │  📦 PARCELAMENTOS EM ANDAMENTO                │  │
│  │  R$ 1.350,00 (parcelas deste mês)             │  │
│  ├────────────────────────────────────────────────┤  │
│  │  • Geladeira Consul                            │  │
│  │    Parcela 5/12 de R$ 350,00                   │  │
│  │    ████████░░░░░░░░░░ 42% completo             │  │
│  │    Restam: 7 parcelas (R$ 2.450 total)        │  │
│  │                                                 │  │
│  │  • Notebook Lenovo                             │  │
│  │    Parcela 3/10 de R$ 500,00                   │  │
│  │    ██████░░░░░░░░░░░░ 30% completo             │  │
│  │    Restam: 7 parcelas (R$ 3.500 total)        │  │
│  │                                                 │  │
│  │  • Sofá 3 Lugares                              │  │
│  │    Parcela 8/12 de R$ 500,00                   │  │
│  │    ████████████████░░ 67% completo             │  │
│  │    Restam: 4 parcelas (R$ 2.000 total)        │  │
│  │                                                 │  │
│  │  💡 Compromisso fixo até término               │  │
│  │  📊 Próximos meses: R$ 1.350/mês               │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  ──────────────────────────────────────────────        │
│  COMPOSIÇÃO DA FATURA:                                │
│  • Gastos ativos: R$ 1.247,90 (44%)                   │
│  • Recorrentes: R$ 250,00 (9%)                        │
│  • Parcelamentos: R$ 1.350,00 (47%)                   │
│  ──────────────────────────────────────────────        │
│                                                        │
│  [Registrar Pagamento] [Baixar Fatura PDF]             │
└────────────────────────────────────────────────────────┘
```

### Previsão de Fatura Futura

```
┌────────────────────────────────────────────────────────┐
│  🔮 PREVISÃO DE FATURAS - Nubank Ultravioleta         │
├────────────────────────────────────────────────────────┤
│                                                        │
│  📊 Próximos 3 Meses (Estimativa)                     │
│                                                        │
│  ┌────────────────────────────────────────────────┐  │
│  │  📅 MARÇO/2026 (Estimado)                      │  │
│  ├────────────────────────────────────────────────┤  │
│  │  Recorrentes (confirmados):      R$ 250,00     │  │
│  │  Parcelamentos (confirmados):    R$ 1.350,00   │  │
│  │  Gastos variáveis (média):       R$ 1.100,00   │  │
│  │  ─────────────────────────────────────────      │  │
│  │  TOTAL PREVISTO:                 R$ 2.700,00   │  │
│  │                                                 │  │
│  │  💡 Baseado na média dos últimos 3 meses       │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  ┌────────────────────────────────────────────────┐  │
│  │  📅 ABRIL/2026 (Estimado)                      │  │
│  ├────────────────────────────────────────────────┤  │
│  │  Recorrentes (confirmados):      R$ 250,00     │  │
│  │  Parcelamentos (confirmados):    R$ 1.350,00   │  │
│  │  Gastos variáveis (média):       R$ 1.100,00   │  │
│  │  ─────────────────────────────────────────      │  │
│  │  TOTAL PREVISTO:                 R$ 2.700,00   │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  ┌────────────────────────────────────────────────┐  │
│  │  📅 MAIO/2026 (Estimado)                       │  │
│  ├────────────────────────────────────────────────┤  │
│  │  Recorrentes (confirmados):      R$ 250,00     │  │
│  │  Parcelamentos (confirmados):    R$ 1.350,00   │  │
│  │  Gastos variáveis (média):       R$ 1.100,00   │  │
│  │  ─────────────────────────────────────────      │  │
│  │  TOTAL PREVISTO:                 R$ 2.700,00   │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  💡 GASTOS FIXOS MENSAIS:                             │
│  Recorrentes + Parcelamentos = R$ 1.600,00            │
│  (Esse valor está garantido todo mês)                  │
│                                                        │
│  🎯 SOBRA PARA GASTOS VARIÁVEIS:                      │
│  Limite R$ 4.000 - Fixos R$ 1.600 = R$ 2.400          │
│  (Você pode gastar até isso em compras mensais)       │
└────────────────────────────────────────────────────────┘
```

### Cadastro de Novo Cartão

```
┌────────────────────────────────────────────┐
│  💳 Adicionar Cartão de Crédito           │
├────────────────────────────────────────────┤
│                                            │
│  Nome do cartão:                           │
│  [Nubank Ultravioleta_____________]        │
│                                            │
│  Bandeira:                                 │
│  ⚪ Visa  ⚫ Mastercard  ⚪ Elo  ⚪ Amex   │
│                                            │
│  Últimos 4 dígitos (opcional):             │
│  **** **** **** [1234]                     │
│                                            │
│  Limite do cartão:                         │
│  R$ [4.000,00]                             │
│                                            │
│  Dia de fechamento da fatura:              │
│  [15 ▼] de cada mês                        │
│                                            │
│  Dia de vencimento:                        │
│  [22 ▼] de cada mês                        │
│                                            │
│  Cor do cartão (para visualização):        │
│  🟣 🔴 🔵 🟢 🟡 ⚫ 🟤                       │
│                                            │
│  Observações:                              │
│  [Cartão principal para compras________]   │
│                                            │
│  [Cancelar]        [Adicionar Cartão]      │
└────────────────────────────────────────────┘
```

### Registro de Gasto no Cartão

```
┌────────────────────────────────────────────┐
│  💳 Novo Gasto no Cartão                  │
├────────────────────────────────────────────┤
│  Selecione o cartão:                       │
│  ⚫ 💳 Nubank Ultravioleta (*1234)         │
│  ⚪ 💳 Inter Black (*5678)                 │
│                                            │
│  Valor:                                    │
│  R$ [___________]                          │
│                                            │
│  Descrição:                                │
│  [Mercado Extra___________________]        │
│                                            │
│  Categoria:                                │
│  [Alimentação ▼]                           │
│                                            │
│  Tipo de gasto:                            │
│  ⚫ Pontual (compra única)                 │
│  ⚪ Recorrente (assinatura/mensalidade)    │
│  ⚪ Parcelado                               │
│                                            │
│  Data:                                     │
│  [05/02/2026 📅]                          │
│                                            │
│  [Cancelar]          [Registrar Gasto]     │
└────────────────────────────────────────────┘
```

### Registro de Gasto Recorrente

```
┌────────────────────────────────────────────┐
│  🔄 Novo Gasto Recorrente                 │
├────────────────────────────────────────────┤
│  Cartão:                                   │
│  [Nubank Ultravioleta ▼]                   │
│                                            │
│  Nome da assinatura/serviço:               │
│  [Netflix Premium________________]         │
│                                            │
│  Valor mensal:                             │
│  R$ [55,90]                                │
│                                            │
│  Categoria:                                │
│  [Entretenimento ▼]                        │
│                                            │
│  Dia de cobrança:                          │
│  Todo dia [01 ▼] do mês                    │
│                                            │
│  Data de início:                           │
│  [01/01/2024 📅]                          │
│                                            │
│  Data de término (opcional):               │
│  ⚫ Indeterminado (até eu cancelar)        │
│  ⚪ Data específica: [_________ 📅]       │
│                                            │
│  Observações:                              │
│  [Plano família 4 telas___________]        │
│                                            │
│  💡 Este gasto aparecerá automaticamente   │
│  todo mês na seção "Recorrentes"           │
│                                            │
│  [Cancelar]    [Cadastrar Recorrente]      │
└────────────────────────────────────────────┘
```

### Registro de Parcelamento

```
┌────────────────────────────────────────────┐
│  📦 Novo Gasto Parcelado                  │
├────────────────────────────────────────────┤
│  Cartão:                                   │
│  [Nubank Ultravioleta ▼]                   │
│                                            │
│  Descrição da compra:                      │
│  [Geladeira Consul Frost Free_____]        │
│                                            │
│  Valor total da compra:                    │
│  R$ [4.200,00]                             │
│                                            │
│  Número de parcelas:                       │
│  [12 ▼] vezes                              │
│                                            │
│  Valor de cada parcela:                    │
│  R$ 350,00 (calculado automaticamente)     │
│                                            │
│  Categoria:                                │
│  [Casa e Móveis ▼]                         │
│                                            │
│  Primeira parcela:                         │
│  [Fevereiro/2026 ▼]                        │
│                                            │
│  ⚪ Com juros                               │
│  ⚫ Sem juros                               │
│                                            │
│  Observações:                              │
│  [Compra na Magazine Luiza_________]       │
│                                            │
│  💡 As parcelas aparecerão automaticamente │
│  nos próximos 12 meses                     │
│                                            │
│  [Cancelar]      [Cadastrar Parcelamento]  │
└────────────────────────────────────────────┘
```

### Alertas de Cartão de Crédito

**Alerta de Proximidade do Limite:**
```
┌─────────────────────────────────────┐
│  ⚠️ Tony Save - Atenção ao Limite  │
├─────────────────────────────────────┤
│  Cartão: Nubank Ultravioleta       │
│                                     │
│  Você usou 80% do limite!           │
│  Usado: R$ 3.200 / R$ 4.000         │
│  Disponível: R$ 800                 │
│                                     │
│  💡 Cuidado com novos gastos        │
│  Faltam 10 dias pro fechamento      │
└─────────────────────────────────────┘
```

**Alerta de Fatura Alta:**
```
┌─────────────────────────────────────┐
│  📊 Tony Save - Fatura Acima Média │
├─────────────────────────────────────┤
│  Cartão: Nubank Ultravioleta       │
│                                     │
│  Fatura atual: R$ 2.847,90          │
│  Média dos últimos 3 meses: R$ 2.100│
│                                     │
│  ⚠️ Você está gastando 36% a mais! │
│                                     │
│  Principais aumentos:               │
│  • Gastos pontuais: +R$ 500         │
│                                     │
│  [Ver Detalhes] [OK]                │
└─────────────────────────────────────┘
```

**Lembrete de Vencimento:**
```
┌─────────────────────────────────────┐
│  📅 Tony Save - Vencimento Próximo │
├─────────────────────────────────────┤
│  Cartão: Nubank Ultravioleta       │
│                                     │
│  Vence em 3 dias! (22/Fev)          │
│  Valor: R$ 2.847,90                 │
│                                     │
│  Já pagou?                          │
│  [Sim, Paguei] [Lembrar Depois]     │
└─────────────────────────────────────┘
```

### Análise de Gastos por Cartão

```
┌────────────────────────────────────────────────────────┐
│  📊 ANÁLISE - Nubank Ultravioleta - Jan/2026          │
├────────────────────────────────────────────────────────┤
│                                                        │
│  Composição da Fatura:                                │
│  ████████████████░░░░ Parcelamentos (47%) R$ 1.350    │
│  ██████████░░░░░░░░░░ Gastos pontuais (44%) R$ 1.248  │
│  ██░░░░░░░░░░░░░░░░░░ Recorrentes (9%) R$ 250         │
│                                                        │
│  Categorias - Gastos Pontuais:                        │
│  ████████████░░░░░░░░ Alimentação (35%) R$ 437        │
│  ██████████░░░░░░░░░░ Transporte (28%) R$ 350         │
│  ██████░░░░░░░░░░░░░░ Compras (20%) R$ 250            │
│  ████░░░░░░░░░░░░░░░░ Saúde (10%) R$ 125              │
│  ██░░░░░░░░░░░░░░░░░░ Lazer (7%) R$ 86                │
│                                                        │
│  Evolução das Faturas:                                │
│  Nov: R$ 2.450 ██████████████████                     │
│  Dez: R$ 2.680 ████████████████████                   │
│  Jan: R$ 2.848 ██████████████████████                 │
│                                                        │
│  💡 Tendência: Aumento de 16% em 3 meses              │
│                                                        │
│  Principais gastos recorrentes:                        │
│  • Academia SmartFit: R$ 89,90/mês                    │
│  • Netflix Premium: R$ 55,90/mês                      │
│  • Spotify Family: R$ 34,90/mês                       │
│                                                        │
│  [Exportar Relatório] [Ver Histórico Completo]        │
└────────────────────────────────────────────────────────┘
```

### Gestão de Gastos Recorrentes

```
┌────────────────────────────────────────────────────────┐
│  🔄 MEUS GASTOS RECORRENTES                           │
├────────────────────────────────────────────────────────┤
│                                                        │
│  💳 Nubank Ultravioleta                               │
│  ┌────────────────────────────────────────────────┐  │
│  │  🎬 Netflix Premium           R$ 55,90/mês     │  │
│  │  Próxima cobrança: 01/Mar                      │  │
│  │  Ativo desde: Jan/2024 (14 meses)              │  │
│  │  [Editar] [Cancelar Assinatura]                │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  ┌────────────────────────────────────────────────┐  │
│  │  🎵 Spotify Family            R$ 34,90/mês     │  │
│  │  Próxima cobrança: 05/Mar                      │  │
│  │  Ativo desde: Mar/2023 (23 meses)              │  │
│  │  [Editar] [Cancelar Assinatura]                │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  ┌────────────────────────────────────────────────┐  │
│  │  💪 Academia SmartFit         R$ 89,90/mês     │  │
│  │  Próxima cobrança: 10/Mar                      │  │
│  │  Ativo desde: Jun/2024 (8 meses)               │  │
│  │  [Editar] [Cancelar Assinatura]                │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  Total recorrente neste cartão: R$ 250,00/mês         │
│                                                        │
│  💳 Inter Black                                       │
│  ┌────────────────────────────────────────────────┐  │
│  │  ☁️ iCloud 200GB              R$ 14,90/mês     │  │
│  │  Próxima cobrança: 20/Mar                      │  │
│  │  [Editar] [Cancelar]                           │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  ──────────────────────────────────────────────        │
│  TOTAL EM ASSINATURAS: R$ 264,90/mês                  │
│  [+ Adicionar Recorrente]                              │
└────────────────────────────────────────────────────────┘
```

### Recursos Avançados

**1. Comparação entre Cartões:**
```
┌──────────────────────────────────────────────┐
│  📊 Comparativo de Cartões - Fev/2026       │
├──────────────────────────────────────────────┤
│                                              │
│  💳 Nubank Ultravioleta                     │
│  Limite: R$ 4.000 | Usado: 71%              │
│  Fatura: R$ 2.847,90                        │
│                                              │
│  💳 Inter Black                             │
│  Limite: R$ 3.000 | Usado: 41%              │
│  Fatura: R$ 1.245,00                        │
│                                              │
│  💡 Sugestão: Próximas compras use Inter    │
│  (tem mais limite disponível)                │
└──────────────────────────────────────────────┘
```

**2. Simulação de Parcelamento:**
```
┌──────────────────────────────────────────────┐
│  🧮 Simulador de Parcelamento               │
├──────────────────────────────────────────────┤
│  Valor da compra: R$ [5.000,00]             │
│                                              │
│  Opções:                                     │
│  • À vista: R$ 5.000,00                     │
│  • 3x sem juros: R$ 1.666,67/mês            │
│  • 6x sem juros: R$ 833,33/mês              │
│  • 12x sem juros: R$ 416,67/mês             │
│                                              │
│  Impacto no limite (12x):                    │
│  Mês 1: -R$ 5.000 (reserva total)           │
│  Libera R$ 416,67 por mês                    │
│                                              │
│  [Simular] [Confirmar Compra]                │
└──────────────────────────────────────────────┘
```

**3. Histórico de Faturas Pagas:**
```
┌──────────────────────────────────────────────┐
│  📜 Histórico - Nubank Ultravioleta         │
├──────────────────────────────────────────────┤
│  ✅ Jan/2026: R$ 2.680 (Pago em 22/Jan)    │
│  ✅ Dez/2025: R$ 2.450 (Pago em 22/Dez)    │
│  ✅ Nov/2025: R$ 2.150 (Pago em 22/Nov)    │
│  ⚠️ Out/2025: R$ 3.100 (Pago c/ atraso)    │
│  ✅ Set/2025: R$ 1.980 (Pago em 22/Set)    │
│                                              │
│  [Ver Mais] [Exportar Histórico]             │
└──────────────────────────────────────────────┘
```

### Integração com Captura Automática

**Quando uma notificação de cartão é capturada:**

```
Sistema detecta: "Nubank: Compra aprovada R$ 85,00 - POSTO SHELL"

┌────────────────────────────────────────────┐
│  💳 Nova Transação Capturada              │
├────────────────────────────────────────────┤
│  Cartão detectado: Nubank Ultravioleta    │
│  Valor: R$ 85,00                          │
│  Local: POSTO SHELL                        │
│  Data: 14/Fev 15:32                       │
│                                            │
│  Categorizar como:                         │
│  [🚗 Transporte] [🍔 Alimentação]         │
│  [💊 Saúde] [🎮 Lazer]                    │
│                                            │
│  Tipo de gasto:                            │
│  ⚫ Pontual  ⚪ Recorrente  ⚪ Parcelado   │
│                                            │
│  [Confirmar]                               │
└────────────────────────────────────────────┘

Após confirmação:
• Adiciona R$ 85 na fatura atual do Nubank
• Classifica como "Gasto Pontual"
• Atualiza percentual de uso do limite
• Sincroniza com web e mobile
```

---

## Fases de Desenvolvimento

### Fase 1: MVP (Produto Mínimo Viável)
- Backend básico com API
- Cadastro de transações (receitas/despesas)
- Dashboard simples com saldo e lista de transações
- App mobile básico
- Notificação push simples

### Fase 2: Funcionalidades Essenciais
- Categorias e filtros
- Gráficos e relatórios
- Múltiplas contas
- Auto-entrada via push notification

### Fase 3: Recursos Avançados
- Metas de economia
- Relatórios avançados
- Anexos de comprovantes
- Exportação de dados (PDF, Excel)
- Modo offline com sincronização

### Fase 4: Inteligência
- Sugestões baseadas em IA
- Detecção de padrões
- Alertas inteligentes
- OCR para digitalizar notas fiscais

---

## Segurança e Privacidade
- [ ] Autenticação segura (JWT, OAuth)
- [ ] Criptografia de dados sensíveis
- [ ] HTTPS obrigatório
- [ ] Backup automático
- [ ] LGPD compliance
- [ ] Autenticação de dois fatores (2FA)

---

## Sistema de Cashback e Benefícios - Detalhamento

### Configuração de Benefícios no Cartão

```
┌────────────────────────────────────────────────────────┐
│  💳 Nubank Ultravioleta - Benefícios                  │
├────────────────────────────────────────────────────────┤
│                                                        │
│  ☑️ Cashback Ativo                                    │
│                                                        │
│  Regras de Cashback:                                   │
│  ┌────────────────────────────────────────────────┐  │
│  │  📊 Padrão (todas as compras)                  │  │
│  │  1% de volta                                    │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  ┌────────────────────────────────────────────────┐  │
│  │  🍔 Alimentação Fora (restaurantes, delivery)  │  │
│  │  5% de volta                                    │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  ┌────────────────────────────────────────────────┐  │
│  │  🛒 Supermercados                              │  │
│  │  2% de volta                                    │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  [+ Adicionar Regra de Cashback]                       │
│                                                        │
│  ─────────────────────────────                         │
│                                                        │
│  ☑️ Programa de Pontos                                │
│                                                        │
│  Programa: [Livelo ▼]                                  │
│  Conversão: 1 ponto por R$ [1,00] gasto               │
│  Validade: [24] meses                                  │
│                                                        │
│  💡 Pontos não expiram se você usar o cartão           │
│                                                        │
│  ─────────────────────────────                         │
│                                                        │
│  Acumulado este mês:                                   │
│  💰 Cashback: R$ 47,50                                 │
│  🎁 Pontos: 2.847 pts                                  │
│                                                        │
│  [Salvar] [Ver Histórico de Benefícios]                │
└────────────────────────────────────────────────────────┘
```

### Transação com Cashback Automático

```
┌────────────────────────────────────────────┐
│  💳 Nova Transação Capturada              │
├────────────────────────────────────────────┤
│  Cartão: Nubank Ultravioleta              │
│  Valor: R$ 85,00                           │
│  Local: iFood - Burguer King               │
│  Data: 14/Fev 15:32                        │
│                                            │
│  Categorizar como:                         │
│  ⚫ 🍔 Alimentação Fora                    │
│  ⚪ 🛒 Supermercados                       │
│  ⚪ 🚗 Transporte                          │
│                                            │
│  ─── Benefícios desta Compra ────          │
│                                            │
│  💰 Cashback: R$ 4,25 (5%)                 │
│  🎁 Pontos: +85 pts                        │
│                                            │
│  💡 Calculado automaticamente              │
│  baseado na categoria selecionada          │
│                                            │
│  Benefício extra/promoção?                 │
│  ☐ Sim, recebi cupom/promoção especial     │
│                                            │
│  [Confirmar]                               │
└────────────────────────────────────────────┘
```

### Ajuste Manual de Benefício (Promoção Especial)

```
┌────────────────────────────────────────────┐
│  🎁 Benefício Extra                       │
├────────────────────────────────────────────┤
│  Transação: R$ 85,00 - iFood              │
│  Cashback padrão: R$ 4,25 (5%)             │
│                                            │
│  ☑️ Recebi benefício extra!               │
│                                            │
│  Tipo:                                     │
│  ⚫ Cupom/Desconto adicional               │
│  ⚪ Promoção temporária do cartão          │
│  ⚪ Cashback especial da loja              │
│                                            │
│  Valor extra:                              │
│  R$ [10,00]                                │
│                                            │
│  Descrição (opcional):                     │
│  [Cupom Black Friday iFood 20% off____]    │
│                                            │
│  ─────────────────────────────              │
│                                            │
│  Total de benefícios:                      │
│  Cashback cartão: R$ 4,25                  │
│  Benefício extra: R$ 10,00                 │
│  TOTAL: R$ 14,25 💚                        │
│                                            │
│  [Cancelar]        [Salvar]                │
└────────────────────────────────────────────┘
```

### Relatório Mensal de Benefícios

```
┌────────────────────────────────────────────────────────┐
│  🎁 RESUMO DE BENEFÍCIOS - Fevereiro/2026             │
├────────────────────────────────────────────────────────┤
│                                                        │
│  💳 Nubank Ultravioleta                               │
│  ┌────────────────────────────────────────────────┐  │
│  │  💰 Cashback Total: R$ 47,50                   │  │
│  │  ████████████████████                          │  │
│  │                                                 │  │
│  │  Detalhamento:                                  │  │
│  │  • 1% padrão: R$ 25,00 (25 transações)         │  │
│  │  • 5% restaurantes: R$ 18,50 (4 transações)    │  │
│  │  • 2% mercados: R$ 4,00 (2 transações)         │  │
│  │                                                 │  │
│  │  Top 3 cashbacks:                               │  │
│  │  1. R$ 7,50 - Outback (15/Fev)                 │  │
│  │  2. R$ 5,00 - iFood (22/Fev)                   │  │
│  │  3. R$ 4,25 - iFood (14/Fev)                   │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  ┌────────────────────────────────────────────────┐  │
│  │  🎁 Pontos Livelo: 2.847 pts                   │  │
│  │  ████████████░░░░░░░░░                         │  │
│  │                                                 │  │
│  │  Equivalência:                                  │  │
│  │  • ~R$ 28,47 em passagens                      │  │
│  │  • ~14 diárias de estacionamento               │  │
│  │  • Faltam 153 pts para resgate mínimo          │  │
│  │                                                 │  │
│  │  Expiram em: Fevereiro/2028 (24 meses)         │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  💳 Inter Black                                       │
│  ┌────────────────────────────────────────────────┐  │
│  │  💰 Cashback Total: R$ 12,45                   │  │
│  │  ████████                                       │  │
│  │  • 0,25% padrão: R$ 12,45 (18 transações)      │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  ──────────────────────────────────────────────        │
│  💰 TOTAL GERAL DO MÊS                                │
│  Cashback: R$ 59,95                                   │
│  Pontos: 2.847 pts                                     │
│  ──────────────────────────────────────────────        │
│                                                        │
│  💡 É como ganhar um lanche grátis todo mês!          │
│                                                        │
│  Histórico anual: R$ 623,45 em cashback (2026)        │
│                                                        │
│  [Ver Histórico Completo] [Resgatar Benefícios]       │
└────────────────────────────────────────────────────────┘
```

---

## Sistema de Reservas e Envelopes Virtuais - Detalhamento

### Dashboard de Envelopes

```
┌────────────────────────────────────────────────────────┐
│  💰 Conta Corrente Nubank                             │
├────────────────────────────────────────────────────────┤
│  Saldo Total: R$ 5.000,00                             │
│                                                        │
│  💼 ENVELOPES/RESERVAS:                                │
│                                                        │
│  ┌────────────────────────────────────────────────┐  │
│  │  🚗 IPVA 2026                                  │  │
│  │  R$ 800,00 / R$ 800,00 ████████████████████  │  │
│  │  Completo! Vence: Março/2026                   │  │
│  │  [Usar] [Editar]                               │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  ┌────────────────────────────────────────────────┐  │
│  │  🏥 Emergência                                 │  │
│  │  R$ 2.500,00 / R$ 3.000,00 ████████████████░░ │  │
│  │  83% - Faltam R$ 500                           │  │
│  │  [+ Depositar] [Editar]                        │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  ┌────────────────────────────────────────────────┐  │
│  │  ✈️ Férias Julho                              │  │
│  │  R$ 1.200,00 / R$ 2.000,00 ████████████░░░░░░ │  │
│  │  60% - Faltam R$ 800                           │  │
│  │  Auto: R$ 400/mês do salário                   │  │
│  │  [+ Depositar] [Editar]                        │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  ┌────────────────────────────────────────────────┐  │
│  │  🎁 Presentes Natal                            │  │
│  │  R$ 500,00 / R$ 1.000,00 ██████████░░░░░░░░░░ │  │
│  │  50% - Faltam R$ 500                           │  │
│  │  [+ Depositar] [Editar]                        │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  ──────────────────────────────────────────────        │
│  Total Reservado: R$ 5.000,00                         │
│  Saldo Disponível: R$ 0,00 ⚠️                         │
│  ──────────────────────────────────────────────        │
│                                                        │
│  💡 Todo seu dinheiro está alocado!                    │
│  Cuidado ao gastar, use apenas se necessário          │
│                                                        │
│  [+ Criar Envelope] [Transferir entre Envelopes]       │
└────────────────────────────────────────────────────────┘
```

### Criar Novo Envelope

```
┌────────────────────────────────────────────┐
│  💼 Criar Envelope/Reserva                │
├────────────────────────────────────────────┤
│                                            │
│  Nome do envelope:                         │
│  [IPVA 2026__________________]             │
│                                            │
│  Ícone:                                    │
│  ⚫ 🚗 Carro  ⚪ 🏥 Saúde  ⚪ ✈️ Viagem    │
│  ⚪ 🎁 Presentes  ⚪ 💰 Genérico           │
│                                            │
│  Meta de valor:                            │
│  R$ [800,00]                               │
│                                            │
│  Depositar agora:                          │
│  R$ [200,00]                               │
│                                            │
│  ☑️ Depósito automático                   │
│  Todo mês, quando receber salário:         │
│  Transferir: R$ [200,00] ou [10] %         │
│  Para este envelope                        │
│                                            │
│  Data limite (opcional):                   │
│  [Março/2026 📅]                          │
│                                            │
│  Observações:                              │
│  [Vencimento do IPVA em março______]       │
│                                            │
│  [Cancelar]        [Criar Envelope]        │
└────────────────────────────────────────────┘
```

### Alerta ao Tentar Gastar Dinheiro Reservado

```
┌────────────────────────────────────────────┐
│  ⚠️ Atenção - Saldo Reservado            │
├────────────────────────────────────────────┤
│  Você está tentando gastar R$ 150,00       │
│                                            │
│  Saldo total: R$ 5.000,00                  │
│  Reservado: R$ 5.000,00                    │
│  Disponível: R$ 0,00 ❌                    │
│                                            │
│  💡 Seu dinheiro está todo alocado:        │
│  • IPVA: R$ 800                            │
│  • Emergência: R$ 2.500                    │
│  • Férias: R$ 1.200                        │
│  • Presentes: R$ 500                       │
│                                            │
│  Deseja continuar mesmo assim?             │
│                                            │
│  ⚪ Sim, usar dinheiro de:                 │
│     [Emergência ▼]                         │
│                                            │
│  ⚪ Não, cancelar esta despesa             │
│                                            │
│  [Cancelar]        [Confirmar]             │
└────────────────────────────────────────────┘
```

---

## Sistema de Garantias - Detalhamento

### Cadastrar Garantia de Produto

```
┌────────────────────────────────────────────────────────┐
│  📦 Nova Garantia de Produto                          │
├────────────────────────────────────────────────────────┤
│                                                        │
│  Nome do produto:                                      │
│  [Geladeira Consul Frost Free 410L________]            │
│                                                        │
│  Categoria:                                            │
│  ⚫ 🏠 Eletrodoméstico  ⚪ 📱 Eletrônico               │
│  ⚪ 🔧 Ferramenta  ⚪ 🚗 Veículo/Peça                 │
│                                                        │
│  Data da compra:                                       │
│  [15/02/2026 📅]                                      │
│                                                        │
│  Prazo de garantia:                                    │
│  [12] meses ou [1] anos                                │
│  Vence em: 15/Fevereiro/2027                           │
│                                                        │
│  Loja/Fornecedor:                                      │
│  [Magazine Luiza_____________________]                 │
│                                                        │
│  Nota Fiscal:                                          │
│  Número: [123456___]                                   │
│  📎 [Anexar foto/PDF da nota]                          │
│                                                        │
│  🔗 Vincular à transação de compra?                    │
│  ⚫ Sim: [15/Fev - Magazine Luiza R$ 2.100 ▼]         │
│  ⚪ Não vincular                                       │
│                                                        │
│  ─── Documentos (Opcional) ────                        │
│  📷 Foto do produto: [Anexar]                          │
│  📄 Certificado de garantia: [Anexar]                  │
│  📖 Manual: [Anexar]                                   │
│                                                        │
│  ─── Dados para Acionar ────                           │
│  Telefone: [(11) 3003-1234____________]                │
│  Site: [magazineluiza.com.br/garantia_]                │
│                                                        │
│  Observações:                                          │
│  [Garantia estendida de 1 ano comprada]                │
│                                                        │
│  ☑️ Notificar 30 dias antes do vencimento             │
│                                                        │
│  [Cancelar]           [Salvar Garantia 📦]             │
└────────────────────────────────────────────────────────┘
```

### Dashboard de Garantias

```
┌────────────────────────────────────────────────────────┐
│  📦 MINHAS GARANTIAS                                  │
├────────────────────────────────────────────────────────┤
│                                                        │
│  Filtros: [Todas ▼] [Ativas] [Vencendo] [Vencidas]   │
│                                                        │
│  ✅ ATIVAS (3)                                        │
│  ┌────────────────────────────────────────────────┐  │
│  │  🏠 Geladeira Consul 410L                      │  │
│  │  Comprada: 15/Fev/2026                         │  │
│  │  Garantia até: 15/Fev/2027 (12 meses)          │  │
│  │  ⏰ Vence em: 365 dias                         │  │
│  │  Loja: Magazine Luiza                          │  │
│  │  Status: ✅ Ativa                              │  │
│  │  [Ver Detalhes] [Editar]                       │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  ┌────────────────────────────────────────────────┐  │
│  │  📱 iPhone 15 Pro Max                          │  │
│  │  Comprada: 20/Jan/2026                         │  │
│  │  Garantia até: 20/Jan/2027 (12 meses)          │  │
│  │  ⏰ Vence em: 340 dias                         │  │
│  │  Loja: Apple Store                             │  │
│  │  Status: ✅ Ativa                              │  │
│  │  [Ver Detalhes] [Editar]                       │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  ⚠️ VENCENDO EM BREVE (1)                             │
│  ┌────────────────────────────────────────────────┐  │
│  │  💻 Notebook Dell Inspiron                     │  │
│  │  Comprada: 10/Mar/2025                         │  │
│  │  Garantia até: 10/Mar/2026 (12 meses)          │  │
│  │  ⚠️ Vence em: 8 dias!                          │  │
│  │  Loja: Dell Online                             │  │
│  │  Status: ⚠️ Vencendo                           │  │
│  │                                                 │  │
│  │  💡 Você pode acionar a garantia agora         │  │
│  │  se houver algum problema!                     │  │
│  │                                                 │  │
│  │  [Ver Detalhes] [Acionar Garantia]             │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  ❌ VENCIDAS (2)                                      │
│  📺 TV Samsung 55" - Venceu há 45 dias                │
│  🔧 Furadeira Bosch - Venceu há 120 dias              │
│                                                        │
│  [+ Nova Garantia]                                     │
└────────────────────────────────────────────────────────┘
```

### Alerta de Vencimento

```
┌─────────────────────────────────────┐
│  ⚠️ Garantia Vencendo!             │
├─────────────────────────────────────┤
│  📱 iPhone 15 Pro Max              │
│                                     │
│  A garantia vence em 30 dias!       │
│  (20/Janeiro/2027)                  │
│                                     │
│  💡 Últimos dias para:              │
│  • Testar todas as funções          │
│  • Verificar defeitos               │
│  • Acionar garantia se necessário   │
│                                     │
│  Tudo funcionando bem?              │
│  [Sim, tá ok] [Acionar Garantia]    │
└─────────────────────────────────────┘
```

---

## Sistema de Eventos - Detalhamento

### Criar Novo Evento

```
┌────────────────────────────────────────────────────────┐
│  🎉 Criar Novo Evento                                 │
├────────────────────────────────────────────────────────┤
│                                                        │
│  Tipo de evento:                                       │
│  ⚫ ✈️ Viagem                                          │
│  ⚪ 💍 Casamento                                       │
│  ⚪ 🎂 Festa/Aniversário                               │
│  ⚪ 🏗️ Reforma/Projeto                                │
│  ⚪ 📚 Curso/Educação                                  │
│  ⚪ 🎯 Outro                                           │
│                                                        │
│  Nome do evento:                                       │
│  [Viagem - Disney Orlando_______________]              │
│                                                        │
│  Período:                                              │
│  Início: [15/07/2026 📅]                              │
│  Fim: [25/07/2026 📅]  (10 dias)                      │
│                                                        │
│  Orçamento total planejado:                            │
│  R$ [15.000,00]                                        │
│                                                        │
│  💰 Como será dividido?                                │
│  ⚫ Só eu pago                                         │
│  ⚪ Dividir com outras pessoas                        │
│                                                        │
│  🌍 Viagem internacional?                              │
│  ☑️ Sim, com conversão de moeda                       │
│  Moeda principal: [USD - Dólar Americano ▼]           │
│                                                        │
│  ─── Categorias do Evento ────                         │
│  (Personalize categorias para este evento)             │
│                                                        │
│  ☑️ Hospedagem           R$ [5.000,00]                │
│  ☑️ Alimentação          R$ [3.000,00]                │
│  ☑️ Transporte           R$ [2.000,00]                │
│  ☑️ Ingressos/Passeios   R$ [4.000,00]                │
│  ☑️ Compras              R$ [1.000,00]                │
│                                                        │
│  [+ Adicionar Categoria]                               │
│                                                        │
│  Observações:                                          │
│  [Férias de julho, família toda_________]              │
│                                                        │
│  [Cancelar]              [Criar Evento 🎉]             │
└────────────────────────────────────────────────────────┘
```

### Evento com Rateio

```
┌────────────────────────────────────────────────────────┐
│  👥 Adicionar Participantes                           │
├────────────────────────────────────────────────────────┤
│  Evento: Viagem - Disney Orlando                       │
│                                                        │
│  Orçamento total: R$ 15.000,00                        │
│                                                        │
│  Quem vai participar?                                  │
│                                                        │
│  ☑️ Você (organizador)                                │
│  ☑️ Maria Silva (esposa)                              │
│  ☑️ João Silva (filho)                                │
│  ☑️ Ana Silva (filha)                                 │
│                                                        │
│  [+ Adicionar Participante]                            │
│                                                        │
│  Como dividir os gastos?                               │
│  ⚫ Dividir igualmente entre adultos (você + Maria)    │
│  ⚪ Dividir igualmente entre todos (4 pessoas)        │
│  ⚪ Personalizar divisão                              │
│                                                        │
│  💡 Crianças não entram na divisão                     │
│                                                        │
│  Divisão:                                              │
│  • Você: 50% (R$ 7.500,00)                            │
│  • Maria: 50% (R$ 7.500,00)                           │
│                                                        │
│  [Voltar]              [Salvar Participantes]          │
└────────────────────────────────────────────────────────┘
```

### Dashboard do Evento (Em Andamento)

```
┌────────────────────────────────────────────────────────┐
│  ✈️ Viagem - Disney Orlando                           │
├────────────────────────────────────────────────────────┤
│  Status: 🟢 Em andamento (Dia 3 de 10)                │
│  Período: 15/Jul - 25/Jul/2026                         │
│                                                        │
│  💰 ORÇAMENTO GERAL                                    │
│  Planejado: R$ 15.000,00                              │
│  Gasto: R$ 8.347,50                                   │
│  ███████████░░░░░░░░░ 56%                             │
│  Restante: R$ 6.652,50 🟢                             │
│                                                        │
│  ─── Gastos por Categoria ────                         │
│                                                        │
│  🏨 Hospedagem: R$ 4.500 / R$ 5.000                   │
│  ██████████████████░░ 90%                             │
│                                                        │
│  🍔 Alimentação: R$ 1.247 / R$ 3.000                  │
│  ████████░░░░░░░░░░░░ 42%                             │
│                                                        │
│  🚗 Transporte: R$ 800 / R$ 2.000                     │
│  ████████░░░░░░░░░░░░ 40%                             │
│                                                        │
│  🎢 Ingressos: R$ 1.800 / R$ 4.000                    │
│  █████████░░░░░░░░░░░ 45%                             │
│                                                        │
│  🛍️ Compras: R$ 0 / R$ 1.000                          │
│  ░░░░░░░░░░░░░░░░░░░░ 0%                              │
│                                                        │
│  ─── Últimas Transações ────                           │
│                                                        │
│  Hoje, 14:32 - Almoço Rainforest Café                 │
│  $47.50 (R$ 247,50) • Pago por: Você                  │
│                                                        │
│  Hoje, 10:15 - Uber até Magic Kingdom                 │
│  $18.00 (R$ 93,60) • Pago por: Maria                  │
│                                                        │
│  Ontem, 19:45 - Jantar Olive Garden                   │
│  $89.30 (R$ 464,76) • Pago por: Você                  │
│                                                        │
│  [+ Novo Gasto] [Ver Todas] [Relatório]               │
│                                                        │
│  ─── Divisão de Gastos ────                            │
│                                                        │
│  Você pagou: R$ 5.200,00 (62%)                        │
│  Maria pagou: R$ 3.147,50 (38%)                       │
│  ────────────────────────────                          │
│  🔄 Maria deve pra você: R$ 1.026,25                  │
│                                                        │
│  [Acertar Contas] [Ver Detalhamento]                  │
└────────────────────────────────────────────────────────┘
```

### Registrar Gasto no Evento

```
┌────────────────────────────────────────────┐
│  💸 Novo Gasto - Disney Orlando           │
├────────────────────────────────────────────┤
│                                            │
│  Descrição:                                │
│  [Almoço Rainforest Café___________]       │
│                                            │
│  💵 Moeda:                                 │
│  ⚫ USD (Dólar)  ⚪ BRL (Real)             │
│                                            │
│  Valor:                                    │
│  $ [47.50]                                 │
│                                            │
│  💱 Conversão (taxa: 1 USD = R$ 5,21):    │
│  R$ 247,50                                 │
│                                            │
│  Categoria:                                │
│  [🍔 Alimentação ▼]                       │
│                                            │
│  Quem pagou?                               │
│  ⚫ Você                                   │
│  ⚪ Maria Silva                            │
│                                            │
│  Dividir entre:                            │
│  ☑️ Você                                  │
│  ☑️ Maria Silva                           │
│  (R$ 123,75 cada)                          │
│                                            │
│  Forma de pagamento:                       │
│  [Cartão Nubank USD ▼]                    │
│                                            │
│  Data/Hora:                                │
│  [17/Jul/2026 14:32 ⏰]                   │
│                                            │
│  [Cancelar]        [Registrar Gasto]       │
└────────────────────────────────────────────┘
```

### Acerto de Contas

```
┌────────────────────────────────────────────────────────┐
│  🔄 Acerto de Contas - Disney Orlando                 │
├────────────────────────────────────────────────────────┤
│                                                        │
│  📊 RESUMO GERAL                                       │
│                                                        │
│  Total gasto: R$ 8.347,50                             │
│  Divisão: 50% cada (você e Maria)                      │
│  Cada um deveria ter pago: R$ 4.173,75                │
│                                                        │
│  ─── Quem Pagou ────                                   │
│                                                        │
│  👤 Você:                                              │
│  Total pago: R$ 5.200,00                              │
│  Deveria: R$ 4.173,75                                 │
│  Diferença: +R$ 1.026,25 (pagou a mais)               │
│                                                        │
│  👤 Maria Silva:                                       │
│  Total pago: R$ 3.147,50                              │
│  Deveria: R$ 4.173,75                                 │
│  Diferença: -R$ 1.026,25 (pagou a menos)              │
│                                                        │
│  ──────────────────────────────────────────────        │
│                                                        │
│  💰 ACERTO:                                            │
│  Maria deve pagar R$ 1.026,25 para você               │
│                                                        │
│  ☐ Já foi acertado                                    │
│                                                        │
│  Chave PIX de Maria: (11) 99999-9999                   │
│  [📋 Copiar]                                           │
│                                                        │
│  [Marcar como Acertado] [Exportar Resumo]              │
└────────────────────────────────────────────────────────┘
```

### Timeline do Evento

```
┌────────────────────────────────────────────────────────┐
│  📅 Timeline - Disney Orlando                         │
├────────────────────────────────────────────────────────┤
│                                                        │
│  ▼ 15/Jul/2026 (Dia 1) - Total: R$ 2.847,50          │
│  ├─ 08:30 - Uber aeroporto → hotel  R$ 156,00        │
│  ├─ 12:00 - Almoço Denny's          R$ 208,00        │
│  ├─ 15:00 - Check-in hotel          R$ 2.340,00      │
│  └─ 20:00 - Jantar Pizza Planet     R$ 143,50        │
│                                                        │
│  ▼ 16/Jul/2026 (Dia 2) - Total: R$ 1.847,20          │
│  ├─ 09:00 - Café da manhã           R$ 104,00        │
│  ├─ 10:30 - Ingresso Magic Kingdom  R$ 1.560,00      │
│  ├─ 13:00 - Almoço no parque        R$ 156,00        │
│  └─ 19:00 - Jantar Be Our Guest     R$ 27,20         │
│                                                        │
│  ▶ 17/Jul/2026 (Dia 3 - Hoje) - Total: R$ 435,10     │
│  ├─ 10:15 - Uber para Magic Kingdom R$ 93,60         │
│  ├─ 14:32 - Almoço Rainforest       R$ 247,50        │
│  └─ 18:00 - Sorvete (previsão)      R$ 94,00         │
│                                                        │
│  ▶ 18/Jul/2026 (Dia 4) - Planejado: R$ 780,00        │
│  └─ Epcot - Ingresso + alimentação                    │
│                                                        │
│  [Ver Gráfico] [Filtrar por Categoria]                │
└────────────────────────────────────────────────────────┘
```

### Relatório Final do Evento

```
┌────────────────────────────────────────────────────────┐
│  📊 RELATÓRIO FINAL - Disney Orlando                  │
├────────────────────────────────────────────────────────┤
│  Status: ✅ Finalizado                                │
│  Período: 15/Jul - 25/Jul/2026 (10 dias)              │
│                                                        │
│  ─── RESUMO FINANCEIRO ────                            │
│                                                        │
│  💰 Orçamento planejado: R$ 15.000,00                 │
│  💸 Total gasto: R$ 14.247,80                         │
│  ✅ Economia: R$ 752,20 (5%)                          │
│                                                        │
│  ─── Gastos por Categoria ────                         │
│                                                        │
│  🏨 Hospedagem                                         │
│  Planejado: R$ 5.000 | Real: R$ 4.680 ✅             │
│  ████████████████████ Economia: R$ 320                │
│                                                        │
│  🍔 Alimentação                                        │
│  Planejado: R$ 3.000 | Real: R$ 3.247 ⚠️             │
│  ███████████████████░ Excesso: R$ 247                 │
│                                                        │
│  🚗 Transporte                                         │
│  Planejado: R$ 2.000 | Real: R$ 1.820 ✅             │
│  ██████████████████░░ Economia: R$ 180                │
│                                                        │
│  🎢 Ingressos/Passeios                                 │
│  Planejado: R$ 4.000 | Real: R$ 3.900 ✅             │
│  ███████████████████░ Economia: R$ 100                │
│                                                        │
│  🛍️ Compras                                            │
│  Planejado: R$ 1.000 | Real: R$ 600 ✅               │
│  ████████████░░░░░░░░ Economia: R$ 400                │
│                                                        │
│  ─── Gastos por Participante ────                      │
│                                                        │
│  👤 Você: R$ 8.450,00 (59%)                           │
│  👤 Maria: R$ 5.797,80 (41%)                          │
│                                                        │
│  🔄 Acerto final:                                      │
│  Maria deve: R$ 326,10 ✅ (Já acertado)               │
│                                                        │
│  ─── Estatísticas ────                                 │
│                                                        │
│  • Gasto médio por dia: R$ 1.424,78                   │
│  • Dia mais caro: 16/Jul (R$ 2.640 - Magic Kingdom)   │
│  • Dia mais barato: 22/Jul (R$ 547 - dia de descanso) │
│  • Refeição mais cara: Be Our Guest (R$ 523)          │
│  • Total de transações: 87                             │
│                                                        │
│  💱 Conversão de Moeda:                                │
│  • Total em USD: $2.456,80                            │
│  • Taxa média: 1 USD = R$ 5,23                        │
│  • Convertido para BRL: R$ 12.849,00                  │
│                                                        │
│  [Exportar PDF] [Compartilhar] [Arquivar Evento]      │
└────────────────────────────────────────────────────────┘
```

### Lista de Eventos

```
┌────────────────────────────────────────────────────────┐
│  🎉 MEUS EVENTOS                                      │
├────────────────────────────────────────────────────────┤
│                                                        │
│  🟢 EM ANDAMENTO (1)                                  │
│  ┌────────────────────────────────────────────────┐  │
│  │  🏗️ Reforma - Cozinha                          │  │
│  │  Orçamento: R$ 8.000 | Gasto: R$ 3.240 (41%)   │  │
│  │  Início: 01/Fev | Fim previsto: 28/Fev         │  │
│  │  [Abrir Evento]                                 │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  📅 PLANEJADOS (2)                                    │
│  ┌────────────────────────────────────────────────┐  │
│  │  🎂 Aniversário 15 anos - Ana                  │  │
│  │  Orçamento: R$ 5.000                            │  │
│  │  Data: 15/Março/2026 (em 28 dias)              │  │
│  │  [Abrir] [Cancelar]                             │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  ┌────────────────────────────────────────────────┐  │
│  │  ✈️ Viagem - Praia (Verão)                     │  │
│  │  Orçamento: R$ 6.000                            │  │
│  │  Período: 20-30/Jan/2027                        │  │
│  │  [Abrir] [Cancelar]                             │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  ✅ FINALIZADOS (3)                                   │
│  ✈️ Disney Orlando - R$ 14.247,80 (Jul/2026)         │
│  💍 Casamento João - R$ 35.000 (Dez/2025)            │
│  🎂 Festa 40 anos - R$ 8.500 (Set/2025)              │
│                                                        │
│  [Ver Arquivados] [+ Novo Evento]                     │
└────────────────────────────────────────────────────────┘
```

### Converter Moeda em Tempo Real

```
┌────────────────────────────────────────────┐
│  💱 Conversor de Moeda                    │
├────────────────────────────────────────────┤
│  Evento: Disney Orlando                    │
│                                            │
│  De: USD (Dólar Americano)                 │
│  $ [100.00]                                │
│                                            │
│  Para: BRL (Real Brasileiro)               │
│  R$ 521,00                                 │
│                                            │
│  Taxa atual: 1 USD = R$ 5,21               │
│  Última atualização: há 5 minutos          │
│                                            │
│  💡 Dica: Taxa favorável hoje!             │
│  Ontem estava R$ 5,28                      │
│                                            │
│  [🔄 Atualizar] [Usar neste Gasto]        │
└────────────────────────────────────────────┘
```

---

## Scanner de Notas Fiscais (OCR) - Detalhamento

### Escanear Nota Fiscal

```
┌────────────────────────────────────────────┐
│  📷 Escanear Nota Fiscal                  │
├────────────────────────────────────────────┤
│                                            │
│  ┌────────────────────────────────────┐  │
│  │                                      │  │
│  │         [Câmera ativa]               │  │
│  │                                      │  │
│  │      Posicione a nota fiscal        │  │
│  │      dentro da moldura               │  │
│  │                                      │  │
│  │   ┌──────────────────────────┐      │  │
│  │   │                          │      │  │
│  │   │                          │      │  │
│  │   │    NOTA FISCAL           │      │  │
│  │   │                          │      │  │
│  │   └──────────────────────────┘      │  │
│  │                                      │  │
│  └────────────────────────────────────┘  │
│                                            │
│  💡 Dica: Certifique-se de que toda       │
│  a nota está visível e bem iluminada      │
│                                            │
│  [📸 Capturar] [🖼️ Galeria] [❌ Cancelar] │
└────────────────────────────────────────────┘
```

### Processando Nota Fiscal

```
┌────────────────────────────────────────────┐
│  ⏳ Processando Nota Fiscal...            │
├────────────────────────────────────────────┤
│                                            │
│  [Imagem da nota capturada]                │
│                                            │
│  🔍 Extraindo informações...               │
│  ████████████████░░ 80%                    │
│                                            │
│  ✓ Loja identificada                       │
│  ✓ Data extraída                           │
│  ✓ Produtos detectados (12 itens)          │
│  ⏳ Processando valores...                 │
│                                            │
│  Aguarde alguns segundos...                │
└────────────────────────────────────────────┘
```

### Revisar Itens Extraídos

```
┌────────────────────────────────────────────────────────┐
│  ✅ Nota Fiscal Processada                            │
├────────────────────────────────────────────────────────┤
│                                                        │
│  Loja: Mercado Extra                                   │
│  Data: 15/02/2026  Hora: 14:32                        │
│  Total: R$ 287,90                                      │
│                                                        │
│  ─── Itens Detectados (12) ────                        │
│                                                        │
│  ☑️ Arroz Tio João 5kg            R$ 28,90            │
│     Categoria: [Alimentação ▼]                        │
│                                                        │
│  ☑️ Feijão Camil 1kg              R$ 8,50             │
│     Categoria: [Alimentação ▼]                        │
│                                                        │
│  ☑️ Leite Integral 1L (3x)        R$ 14,97            │
│     Categoria: [Alimentação ▼]                        │
│                                                        │
│  ☑️ Papel Higiênico 12 rolos      R$ 22,90            │
│     Categoria: [Higiene/Limpeza ▼]                    │
│                                                        │
│  ☑️ Detergente Ypê (2x)           R$ 5,98             │
│     Categoria: [Higiene/Limpeza ▼]                    │
│                                                        │
│  ☑️ Carne Moída 1kg               R$ 35,00            │
│     Categoria: [Alimentação ▼]                        │
│                                                        │
│  [Mostrar todos os 12 itens]                           │
│                                                        │
│  💡 Revise os itens e categorias                       │
│                                                        │
│  Como registrar?                                       │
│  ⚫ Uma transação com todos itens (R$ 287,90)         │
│  ⚪ Transações separadas por categoria                │
│                                                        │
│  Conta: [Conta Corrente Nubank ▼]                    │
│  Método: [Cartão de Débito ▼]                         │
│                                                        │
│  [Editar Itens] [❌ Cancelar] [✅ Confirmar]          │
└────────────────────────────────────────────────────────┘
```

### Análise de Produtos (Após várias compras)

```
┌────────────────────────────────────────────────────────┐
│  📊 Análise de Produtos - Arroz Tio João 5kg          │
├────────────────────────────────────────────────────────┤
│                                                        │
│  Histórico de Compras:                                 │
│                                                        │
│  📅 15/Fev/2026 - Mercado Extra      R$ 28,90         │
│  📅 30/Jan/2026 - Carrefour          R$ 29,50         │
│  📅 12/Jan/2026 - Mercado Extra      R$ 27,90         │
│  📅 28/Dez/2025 - Extra              R$ 28,00         │
│  📅 10/Dez/2025 - Mercado Extra      R$ 27,50         │
│                                                        │
│  ─── Estatísticas ────                                 │
│                                                        │
│  Frequência: A cada 15-17 dias                         │
│  Preço médio: R$ 28,36                                │
│  Menor preço: R$ 27,50 (Extra - 10/Dez)               │
│  Maior preço: R$ 29,50 (Carrefour - 30/Jan)           │
│                                                        │
│  Tendência: 📈 Subindo (+3% em 2 meses)               │
│                                                        │
│  💡 Você costuma comprar no Mercado Extra (60%)        │
│                                                        │
│  🔔 Alertas:                                           │
│  ☑️ Notificar quando preço baixar de R$ 27,50        │
│  ☑️ Lembrar de comprar em 3 dias (baseado na freq.)   │
│                                                        │
│  [Ver Gráfico] [Configurar Alertas]                   │
└────────────────────────────────────────────────────────┘
```

---

## Simulador de Cenários - Detalhamento

### Tela Principal do Simulador

```
┌────────────────────────────────────────────────────────┐
│  🔮 Simulador de Cenários Financeiros                 │
├────────────────────────────────────────────────────────┤
│                                                        │
│  💡 Veja o impacto de mudanças no seu orçamento       │
│                                                        │
│  CENÁRIO ATUAL:                                        │
│  Receitas: R$ 3.800/mês                               │
│  Despesas: R$ 2.850/mês                               │
│  Sobra: R$ 950/mês                                    │
│                                                        │
│  ─── Criar Nova Simulação ────                         │
│                                                        │
│  O que você quer simular?                              │
│                                                        │
│  ⚪ Cancelar assinatura/serviço                       │
│  ⚪ Adicionar nova despesa recorrente                 │
│  ⚪ Mudar de emprego (salário diferente)              │
│  ⚪ Quitar dívida/empréstimo                          │
│  ⚪ Trocar de carro/moradia                           │
│  ⚫ Simulação customizada                             │
│                                                        │
│  ─── Cenários Predefinidos ────                        │
│                                                        │
│  🔴 Modo Economia Extrema                             │
│  Cancela tudo que não é essencial                      │
│  Economia: +R$ 450/mês                                │
│  [Simular]                                             │
│                                                        │
│  💰 Modo Investidor                                    │
│  Maximiza poupança e investimentos                     │
│  Economia: +R$ 350/mês                                │
│  [Simular]                                             │
│                                                        │
│  📉 Modo Quitação de Dívidas                          │
│  Prioriza pagar todas as dívidas                       │
│  Tempo para quitar: 8 meses                            │
│  [Simular]                                             │
│                                                        │
│  [+ Nova Simulação Customizada]                        │
└────────────────────────────────────────────────────────┘
```

### Exemplo: Cancelar Assinaturas

```
┌────────────────────────────────────────────────────────┐
│  🔮 Simulação: Cancelar Assinaturas                   │
├────────────────────────────────────────────────────────┤
│                                                        │
│  Selecione o que deseja cancelar:                      │
│                                                        │
│  ☑️ Netflix Premium               R$ 55,90/mês        │
│  ☑️ Spotify Family                R$ 34,90/mês        │
│  ☐ Amazon Prime                   R$ 14,90/mês        │
│  ☐ Xbox Game Pass                 R$ 39,50/mês        │
│  ☐ Academia SmartFit              R$ 89,90/mês        │
│                                                        │
│  Total a economizar: R$ 90,80/mês                     │
│                                                        │
│  ──────────────────────────────────────────────        │
│                                                        │
│  📊 COMPARAÇÃO: ATUAL vs SIMULADO                     │
│                                                        │
│  ┌────────────────────┬────────────────────┐          │
│  │      ATUAL         │     SIMULADO       │          │
│  ├────────────────────┼────────────────────┤          │
│  │ Receitas           │ Receitas           │          │
│  │ R$ 3.800           │ R$ 3.800           │          │
│  │                    │                    │          │
│  │ Despesas           │ Despesas           │          │
│  │ R$ 2.850           │ R$ 2.759,20 ✅    │          │
│  │                    │                    │          │
│  │ Sobra Mensal       │ Sobra Mensal       │          │
│  │ R$ 950             │ R$ 1.040,80 📈    │          │
│  │                    │                    │          │
│  │ Poupança Anual     │ Poupança Anual     │          │
│  │ R$ 11.400          │ R$ 12.489,60 🎉   │          │
│  └────────────────────┴────────────────────┘          │
│                                                        │
│  💰 ECONOMIA TOTAL: +R$ 1.089,60 por ano!             │
│                                                        │
│  🎯 IMPACTO NAS METAS:                                │
│  • Notebook Gamer: -2 meses (junho → abril)           │
│  • Viagem Disney: -3 meses (mar/27 → dez/26)          │
│                                                        │
│  💡 Com essa economia você alcança metas mais rápido!  │
│                                                        │
│  [Salvar Cenário] [Aplicar ao Orçamento] [Descartar]  │
└────────────────────────────────────────────────────────┘
```

### Exemplo: Mudar de Emprego

```
┌────────────────────────────────────────────────────────┐
│  🔮 Simulação: Mudança de Emprego                     │
├────────────────────────────────────────────────────────┤
│                                                        │
│  Novo salário proposto:                                │
│  R$ [4.500,00]                                         │
│                                                        │
│  Novas despesas (se houver):                           │
│  ☑️ Vale transporte menor  -R$ 50/mês                 │
│  ☑️ Gasolina (+ distância) +R$ 200/mês                │
│  ☐ Plano de saúde empresa  -R$ 150/mês                │
│                                                        │
│  ──────────────────────────────────────────────        │
│                                                        │
│  📊 COMPARAÇÃO                                         │
│                                                        │
│  Emprego Atual:                                        │
│  Salário: R$ 3.000                                    │
│  Despesas relacionadas: R$ 250                         │
│  Líquido efetivo: R$ 2.750                            │
│                                                        │
│  Novo Emprego:                                         │
│  Salário: R$ 4.500                                    │
│  Despesas relacionadas: R$ 400                         │
│  Líquido efetivo: R$ 4.100                            │
│                                                        │
│  💰 GANHO REAL: +R$ 1.350/mês (+49%)                  │
│  📈 GANHO ANUAL: +R$ 16.200                           │
│                                                        │
│  🎯 IMPACTO:                                          │
│  • Sobra mensal: R$ 950 → R$ 2.300 (+142%)            │
│  • Todas metas alcançadas 60% mais rápido             │
│  • Reserva emergência completa em 3 meses             │
│                                                        │
│  💡 VALE A PENA! Aceite a proposta! 🎉                │
│                                                        │
│  [Salvar Simulação] [Voltar]                           │
└────────────────────────────────────────────────────────┘
```

---

## Lista de Compras Inteligente - Detalhamento

### Criar Lista de Compras

```
┌────────────────────────────────────────────────────────┐
│  🛒 Nova Lista de Compras                             │
├────────────────────────────────────────────────────────┤
│                                                        │
│  Nome da lista:                                        │
│  [Mercado do Mês_____________________]                 │
│                                                        │
│  Categoria vinculada:                                  │
│  [Alimentação ▼]                                       │
│                                                        │
│  💰 Orçamento disponível:                              │
│  Categoria Alimentação: R$ 900,00                      │
│  Já gasto este mês: R$ 347,90                         │
│  ────────────────────────────────                      │
│  Disponível: R$ 552,10 ✅                             │
│                                                        │
│  Limite para esta compra:                              │
│  R$ [300,00]                                           │
│                                                        │
│  ─── Sugestões Baseadas no Histórico ────              │
│                                                        │
│  💡 Produtos que você costuma comprar:                 │
│  ☐ Arroz Tio João 5kg (compra a cada 15 dias)        │
│  ☐ Feijão Camil 1kg (compra a cada 20 dias)          │
│  ☐ Papel higiênico (última compra há 23 dias)        │
│  ☐ Leite integral 1L (compra semanalmente)           │
│                                                        │
│  [Adicionar Sugeridos]                                 │
│                                                        │
│  [Criar Lista] [Cancelar]                              │
└────────────────────────────────────────────────────────┘
```

### Durante as Compras

```
┌────────────────────────────────────────────────────────┐
│  🛒 Mercado do Mês                                    │
├────────────────────────────────────────────────────────┤
│                                                        │
│  💰 ORÇAMENTO                                          │
│  Limite: R$ 300,00                                    │
│  Gasto: R$ 187,40                                     │
│  ████████████░░░░░░░ 62%                              │
│  Restante: R$ 112,60 🟢                               │
│                                                        │
│  ─── Produtos (8/12) ────                              │
│                                                        │
│  ✅ Arroz Tio João 5kg         R$ 28,90               │
│  ✅ Feijão Camil 1kg           R$ 8,50                │
│  ✅ Leite 1L (x3)              R$ 14,97               │
│  ✅ Papel higiênico 12 rolos   R$ 22,90               │
│  ✅ Carne moída 1kg            R$ 35,00               │
│  ✅ Frango 1kg                 R$ 18,90               │
│  ✅ Tomate 1kg                 R$ 8,90                │
│  ✅ Banana 1kg                 R$ 6,50                │
│                                                        │
│  ⏹️ Macarrão 500g               R$ 4,50                │
│  ⏹️ Óleo de soja 900ml          R$ 7,90                │
│  ⏹️ Açúcar 1kg                  R$ 5,50                │
│  ⏹️ Café 500g                   R$ 12,00               │
│                                                        │
│  [+ Adicionar Item]                                    │
│                                                        │
│  💡 Você ainda pode gastar R$ 112,60                   │
│  Itens restantes custariam: R$ 29,90                   │
│  Sobraria: R$ 82,70 ✅                                │
│                                                        │
│  [Finalizar Compra] [Escanear Nota]                   │
└────────────────────────────────────────────────────────┘
```

### Alerta de Estouro de Orçamento

```
┌────────────────────────────────────────────┐
│  ⚠️ Atenção - Orçamento Ultrapassado     │
├────────────────────────────────────────────┤
│  Você adicionou:                           │
│  Vinho Tinto 750ml - R$ 45,00              │
│                                            │
│  Limite: R$ 300,00                         │
│  Total atual: R$ 332,40                    │
│  Excesso: R$ 32,40 ❌                      │
│                                            │
│  O que deseja fazer?                       │
│                                            │
│  ⚪ Remover este item                      │
│  ⚪ Aumentar limite da lista               │
│  ⚪ Continuar assim mesmo                  │
│     (usar dinheiro de outra categoria)     │
│                                            │
│  💡 Você ainda tem R$ 252 disponíveis      │
│  em "Lazer" que poderia usar               │
│                                            │
│  [Decidir]                                 │
└────────────────────────────────────────────┘
```

---

## Comparador de Preços Histórico - Detalhamento

### Rastrear Produto

```
┌────────────────────────────────────────────┐
│  📊 Adicionar Produto ao Rastreamento     │
├────────────────────────────────────────────┤
│                                            │
│  Produto:                                  │
│  [Gasolina Comum______________]            │
│                                            │
│  Tipo:                                     │
│  ⚫ Combustível (R$/litro)                 │
│  ⚪ Produto de supermercado (R$/unidade)  │
│  ⚪ Gás de cozinha (R$/botijão)           │
│                                            │
│  Estabelecimento:                          │
│  [Posto Ipiranga Av. Paulista____]         │
│                                            │
│  Preço hoje:                               │
│  R$ [5,89] / litro                         │
│                                            │
│  ☑️ Rastrear automaticamente              │
│  ☑️ Alertar se variar mais de 5%          │
│                                            │
│  [Cancelar]        [Iniciar Rastreamento]  │
└────────────────────────────────────────────┘
```

### Dashboard de Comparação

```
┌────────────────────────────────────────────────────────┐
│  📊 COMPARADOR DE PREÇOS                              │
├────────────────────────────────────────────────────────┤
│                                                        │
│  ⛽ Gasolina Comum                                     │
│  ┌────────────────────────────────────────────────┐  │
│  │  Evolução (últimos 3 meses)                    │  │
│  │  ────────────────────────────────────────       │  │
│  │  Fev  5.89 ████████████████████ 📈            │  │
│  │  Jan  5.75 ██████████████████░░                │  │
│  │  Dez  5.69 █████████████████░░░                │  │
│  │  Nov  5.82 ███████████████████░                │  │
│  │                                                 │  │
│  │  Tendência: 📈 Subindo (+3,5% em 3 meses)     │  │
│  │  Variação: +R$ 0,20/litro                      │  │
│  │                                                 │  │
│  │  Média: R$ 5,79/litro                          │  │
│  │  Menor: R$ 5,69 (17/Dez - Posto Shell)        │  │
│  │  Maior: R$ 5,89 (Hoje - Ipiranga)             │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  🏪 Comparação de Postos (Hoje):                      │
│  ┌────────────────────────────────────────────────┐  │
│  │  🟢 Posto Shell Centro        R$ 5,79/L        │  │
│  │  🟡 Posto BR Av. Brasil       R$ 5,85/L        │  │
│  │  🔴 Ipiranga Av. Paulista     R$ 5,89/L        │  │
│  │                                                 │  │
│  │  💡 Economia: R$ 0,10/litro no Shell           │  │
│  │  Abastecendo 40L: Economiza R$ 4,00            │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  🍚 Arroz Tio João 5kg                                │
│  ┌────────────────────────────────────────────────┐  │
│  │  Preço atual: R$ 28,90                         │  │
│  │  ✅ MENOR PREÇO DOS ÚLTIMOS 6 MESES!          │  │
│  │                                                 │  │
│  │  💰 Vale a pena comprar AGORA!                 │  │
│  │  Preço médio: R$ 29,80                         │  │
│  │  Você economiza: R$ 0,90 (-3%)                 │  │
│  └────────────────────────────────────────────────┘  │
│                                                        │
│  [+ Adicionar Produto] [Ver Todos]                    │
└────────────────────────────────────────────────────────┘
```

### Alerta de Preço

```
┌─────────────────────────────────────┐
│  💰 Alerta de Preço!               │
├─────────────────────────────────────┤
│  Produto: Arroz Tio João 5kg       │
│                                     │
│  🎉 MENOR PREÇO EM 6 MESES!        │
│                                     │
│  Preço atual: R$ 27,50              │
│  Preço médio: R$ 29,20              │
│  Economia: R$ 1,70 (-6%)            │
│                                     │
│  Local: Mercado Extra               │
│                                     │
│  💡 É hora de comprar!              │
│  Você costuma comprar esse produto  │
│  a cada 15 dias                     │
│                                     │
│  [Ver Detalhes] [Adicionar à Lista] │
└─────────────────────────────────────┘
```

---

## Perguntas para Definir

1. **Usuário:** Pessoal ou suportar múltiplos usuários/família?
2. **Moeda:** Apenas BRL ou multi-moeda?
3. **Recorrência:** Suportar contas fixas mensais (aluguel, assinaturas)?
4. **Integração bancária:** Importar extratos automaticamente (Open Banking)?
5. **Plataforma prioritária:** Web ou Mobile primeiro?
6. **Hospedagem:** Cloud (AWS, Azure, GCP) ou self-hosted?

---

## Funcionalidades Futuras (Roadmap)

### 1. Modo Casal/Família Compartilhado
- [ ] **Múltiplos usuários no mesmo app:**
  - [ ] Cadastrar membros da família
  - [ ] Permissões por usuário (admin, visualizador, editor)
  - [ ] Cada pessoa com login próprio
- [ ] **Contas compartilhadas:**
  - [ ] Marcar conta como compartilhada (ex: conta conjunta)
  - [ ] Todos os membros veem transações dessa conta
  - [ ] Contas individuais (só o dono vê)
- [ ] **Despesas compartilhadas vs individuais:**
  - [ ] Marcar despesa como "compartilhada" ou "individual"
  - [ ] Dividir automaticamente entre membros
  - [ ] "Quem paga o quê" (aluguel dividido, mercado dividido)
- [ ] **Metas familiares:**
  - [ ] Metas compartilhadas (economizar para casa, viagem)
  - [ ] Todos contribuem e acompanham progresso
  - [ ] Histórico de quem depositou quanto
- [ ] **Dashboard familiar:**
  - [ ] Visão geral de finanças da família
  - [ ] Gastos por membro
  - [ ] Orçamento familiar vs individual
- [ ] Notificações entre membros
- [ ] Privacidade configurável (o que cada um pode ver)

### 4. Assistente Financeiro com IA
- [ ] **Chatbot inteligente:**
  - [ ] Responder perguntas sobre finanças
  - [ ] "Quanto gastei em restaurantes este mês?"
  - [ ] "Posso comprar um produto de R$ 500?"
  - [ ] "Quando vou atingir a meta X?"
- [ ] **Sugestões proativas:**
  - [ ] "Você gasta muito em categoria X, considere reduzir"
  - [ ] "Cancele assinatura Y e economize R$ Z/mês"
  - [ ] "Vale a pena trocar de emprego pela proposta"
- [ ] **Análise de padrões:**
  - [ ] Detectar comportamentos financeiros
  - [ ] "Você gasta mais nos finais de semana"
  - [ ] "Todo mês após receber salário, gasta 40% a mais"
- [ ] **Comandos por voz:**
  - [ ] "Ok Tony, registrar gasto de R$ 50 em alimentação"
  - [ ] "Quanto tenho disponível?"
- [ ] Aprendizado contínuo (melhora com o uso)
- [ ] Integração com assistentes (Google, Alexa)

### 5. Controle de Investimentos
- [ ] **Cadastrar investimentos:**
  - [ ] Ações, FIIs, Fundos, CDB, Tesouro Direto
  - [ ] Criptomoedas
  - [ ] Quantidade, valor de compra, corretora
- [ ] **Acompanhar rentabilidade:**
  - [ ] Valor atual vs valor investido
  - [ ] Lucro/prejuízo por ativo
  - [ ] Rentabilidade percentual
- [ ] **Integração com APIs:**
  - [ ] Cotação em tempo real (B3, CoinMarketCap)
  - [ ] Atualização automática de valores
- [ ] **Patrimônio total:**
  - [ ] Saldo em contas + investimentos
  - [ ] Gráfico de evolução patrimonial
  - [ ] Diversificação (% em cada tipo de ativo)
- [ ] **Dividendos e rendimentos:**
  - [ ] Registrar recebimento de dividendos
  - [ ] Previsão de próximos dividendos
  - [ ] Total recebido no ano
- [ ] Relatórios de performance
- [ ] IR (imposto sobre ganhos)

### 7. Controle de Patrimônio
- [ ] **Registrar bens:**
  - [ ] Casa, apartamento, terreno
  - [ ] Carro, moto, barco
  - [ ] Eletrônicos, móveis
  - [ ] Joias, coleções
- [ ] **Informações do bem:**
  - [ ] Valor de compra
  - [ ] Data de aquisição
  - [ ] Valor de mercado atual
  - [ ] Fotos/documentos
- [ ] **Depreciação automática:**
  - [ ] Carros (tabela FIPE)
  - [ ] Eletrônicos (% ao ano)
  - [ ] Atualização de valor de mercado
- [ ] **Patrimônio líquido:**
  - [ ] Total em bens + contas + investimentos
  - [ ] Menos dívidas
  - [ ] Evolução ao longo do tempo
- [ ] **Gráfico patrimonial:**
  - [ ] Distribuição (imóveis, veículos, eletrônicos)
  - [ ] Evolução mensal/anual
  - [ ] Comparação com períodos anteriores
- [ ] Alertas de renovação (seguro, documentos)
- [ ] Histórico de valorização/desvalorização

### 9. Calendário Financeiro Visual
- [ ] **Visão mensal em calendário:**
  - [ ] Receitas marcadas em verde
  - [ ] Despesas marcadas em vermelho
  - [ ] Vencimentos destacados
  - [ ] Eventos financeiros
- [ ] **Informações por dia:**
  - [ ] Click no dia → ver todas transações
  - [ ] Saldo previsto para aquele dia
  - [ ] Lembretes do dia
- [ ] **Visão de múltiplos meses:**
  - [ ] Ver 3-6 meses de uma vez
  - [ ] Planejar com antecedência
  - [ ] Identificar padrões visuais
- [ ] **Legenda visual:**
  - [ ] Cores por categoria
  - [ ] Ícones por tipo (salário, conta, compra)
  - [ ] Intensidade por valor
- [ ] **Integração com apps de calendário:**
  - [ ] Exportar eventos para Google Calendar
  - [ ] Sincronização bidirecional
  - [ ] Lembretes no calendário nativo
- [ ] Modo timeline (linha do tempo)
- [ ] Filtros por categoria/conta

### 10. Modo Offline Completo
- [ ] **Funcionar 100% sem internet:**
  - [ ] Banco de dados local
  - [ ] Todas funcionalidades disponíveis
  - [ ] Registrar transações offline
  - [ ] Consultar dados offline
- [ ] **Sincronização inteligente:**
  - [ ] Detecta quando conecta
  - [ ] Sincroniza automaticamente
  - [ ] Resolução de conflitos
  - [ ] Fila de sincronização
- [ ] **Indicador de status:**
  - [ ] Ícone mostrando se está online/offline
  - [ ] Quantidade de itens pendentes de sincronização
  - [ ] Última sincronização
- [ ] **Backup local:**
  - [ ] Dados salvos no dispositivo
  - [ ] Não perde nada se ficar offline muito tempo
- [ ] Essencial para viagens sem sinal
- [ ] Funciona em modo avião

### 11. Widget para Tela Inicial (Mobile)
- [ ] **Widget pequeno:**
  - [ ] Saldo disponível
  - [ ] Próximo vencimento
  - [ ] Botão de registro rápido
- [ ] **Widget médio:**
  - [ ] Saldo total e disponível
  - [ ] Próximas 3 contas a pagar
  - [ ] Resumo do mês
- [ ] **Widget grande:**
  - [ ] Dashboard completo
  - [ ] Gráfico de gastos
  - [ ] Metas em andamento
  - [ ] Transações recentes
- [ ] **Ações rápidas no widget:**
  - [ ] Registrar gasto (abre formulário)
  - [ ] Ver extrato
  - [ ] Abrir app direto na tela
- [ ] Personalização de cores
- [ ] Atualização em tempo real
- [ ] Múltiplos widgets (um para cada conta)

### 12. Integração Open Banking (Avançado)
- [ ] **Conectar com banco via Open Banking:**
  - [ ] Autorização segura (OAuth)
  - [ ] Conexão direta com API do banco
  - [ ] Sem necessidade de notificações
- [ ] **Sincronização automática:**
  - [ ] Importar transações automaticamente
  - [ ] Atualização em tempo real
  - [ ] Saldo atualizado direto do banco
- [ ] **Suporte a múltiplos bancos:**
  - [ ] Nubank, Inter, Itaú, Bradesco, etc.
  - [ ] Contas de múltiplos bancos
  - [ ] Consolidação automática
- [ ] **Categorização automática:**
  - [ ] IA aprende com suas categorizações
  - [ ] Sugere categoria para novas transações
  - [ ] Melhora com o tempo
- [ ] **Segurança:**
  - [ ] Conexão criptografada
  - [ ] Tokens temporários
  - [ ] Revogação de acesso a qualquer momento
- [ ] Atualização de saldo em tempo real
- [ ] Histórico completo importado

### 13. Segurança e Privacidade

#### Modo Oculto (Esconder Saldos)
- [ ] **Botão rápido para ocultar valores:**
  - [ ] Ícone de olho no header/navbar
  - [ ] Um toque esconde todos os saldos
  - [ ] Valores substituídos por "R$ ••••••" ou "******"
  - [ ] Atalho de gesto (shake do celular, por exemplo)
- [ ] **Configurações do modo oculto:**
  - [ ] Ocultar saldo total
  - [ ] Ocultar saldos por conta
  - [ ] Ocultar valores de transações
  - [ ] Ocultar limites de cartão
  - [ ] Ocultar metas e reservas
- [ ] **Comportamento inteligente:**
  - [ ] Ativar automaticamente em redes Wi-Fi públicas
  - [ ] Ativar ao detectar múltiplos rostos na câmera (opcional)
  - [ ] Lembrar preferência por tela/página
  - [ ] Timeout automático (revelar após X segundos)
- [ ] Revelar valor individual com toque longo
- [ ] Animação suave ao ocultar/revelar
- [ ] Funciona em todas as telas do app

#### Sistema de Autenticação Avançada (Futuro)
- [ ] **Autenticação estilo Steam Guard:**
  - [ ] Código rotativo a cada 30 segundos
  - [ ] Gerador de código no próprio app
  - [ ] Necessário para operações sensíveis
  - [ ] Backup de códigos de recuperação
- [ ] **Autenticação biométrica:**
  - [ ] Face ID / Reconhecimento facial
  - [ ] Touch ID / Impressão digital
  - [ ] Configurar quais ações exigem biometria
- [ ] **Níveis de segurança configuráveis:**
  - [ ] Apenas para abrir o app
  - [ ] Para ver saldos
  - [ ] Para realizar transações
  - [ ] Para exportar dados
  - [ ] Para alterar configurações
- [ ] **Proteções extras:**
  - [ ] PIN de acesso (4-6 dígitos)
  - [ ] Padrão de desbloqueio
  - [ ] Bloqueio automático após X minutos
  - [ ] Alerta de tentativas falhas de login
  - [ ] Bloqueio temporário após várias tentativas
- [ ] **Dispositivos confiáveis:**
  - [ ] Lista de dispositivos autorizados
  - [ ] Notificação de novo acesso
  - [ ] Revogar acesso de dispositivo remotamente

---

## Próximos Passos
- [ ] Definir stack tecnológico
- [ ] Criar wireframes/mockups
- [ ] Definir modelo de dados
- [ ] Configurar ambiente de desenvolvimento
- [ ] Implementar MVP

---

## Notas para Manutenção da Documentação

> **IMPORTANTE:** Este documento deve ser atualizado sempre que novas regras de negócio ou funcionalidades forem definidas durante o desenvolvimento.
>
> Ao definir uma nova funcionalidade ou regra:
> - Adicionar na seção de funcionalidades correspondente
> - Detalhar comportamento esperado
> - Atualizar data de última atualização
>
> Manter sincronizado com: SSR.md e DESENVOLVIMENTO.md
