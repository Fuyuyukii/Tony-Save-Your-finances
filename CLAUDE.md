# CLAUDE.md - Instruções para o Assistente

## Contexto do Projeto

Este é o projeto **Tony Save Your Finances**, um sistema de controle financeiro pessoal multiplataforma.

## Antes de Iniciar

**IMPORTANTE:** Antes de começar qualquer tarefa, leia os seguintes arquivos para contexto completo:

1. **[PLANEJAMENTO.md](PLANEJAMENTO.md)** - Visão geral do produto, funcionalidades planejadas e regras de negócio
2. **[DESENVOLVIMENTO.md](DESENVOLVIMENTO.md)** - Stack tecnológica, arquitetura, fases de desenvolvimento e tarefas pendentes
3. **[SSR.md](SSR.md)** - Requisitos funcionais e não-funcionais, casos de uso e regras de negócio formalizadas

## Stack Tecnológica

- **Backend**: NestJS + Fastify + TypeScript + Prisma + PostgreSQL
- **Frontend Web**: React + Vite + TypeScript + Tailwind
- **Mobile**: React Native + Expo + Expo Router + NativeWind
- **Infraestrutura**: Railway (backend) + Vercel (frontend) + Neon (banco)

## Diretrizes de Desenvolvimento

1. **MVP First** - Priorizar funcionalidades essenciais antes de features avançadas
2. **Paridade Web/Mobile** - Funcionalidades devem estar disponíveis em ambas plataformas
3. **TypeScript Strict** - Tipagem forte em todo o código
4. **Componentes Reutilizáveis** - Usar CVA para variantes de componentes
5. **Layout Consistente** - Todos os cards, containers e componentes devem manter altura e estrutura fixa, independentemente da quantidade de conteúdo. Use `flex-shrink-0` para elementos fixos, `flex-grow` com `min-h-[valor]` para áreas variáveis, e `truncate` para textos longos. Isso garante que o layout nunca quebre ou desalinhe mesmo com mais ou menos informações.

## Estrutura do Projeto

```
/
├── apps/
│   ├── api/          # Backend NestJS
│   ├── web/          # Frontend React
│   └── mobile/       # App React Native
├── packages/
│   └── shared/       # Tipos e utils compartilhados
└── docs/             # Documentação adicional
```

## Comandos Úteis

```bash
# Instalar dependências
pnpm install

# Rodar backend
pnpm --filter api dev

# Rodar frontend web
pnpm --filter web dev

# Rodar mobile
pnpm --filter mobile start
```

## Protocolo de Conclusão de Tarefas

**SEMPRE** que finalizar uma tarefa, forneça um resumo completo incluindo:

1. **Requisição Original**: O que o usuário pediu
2. **Contexto**: A situação ou problema sendo abordado
3. **O Que Foi Feito**: Lista detalhada de mudanças, implementações ou soluções
4. **Arquivos Modificados**: Lista de todos os arquivos alterados com breve descrição das mudanças
5. **Detalhes Técnicos**: Padrões de código chave, funções ou decisões arquiteturais
6. **Verificação**: Como a solução foi verificada

Isso ajuda a manter o contexto através de múltiplas sessões de trabalho e abas do navegador.
