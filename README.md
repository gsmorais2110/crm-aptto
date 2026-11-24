# CRM Aptto — Vendas

CRM web para a equipe de vendas e implantação do sistema PDV Aptto (A.A Tecnologia).

Stack: Next.js 16, React 19, Tailwind 4, Supabase (PostgreSQL + Auth), Recharts.

## Rodar em modo demo (sem Supabase)

```bash
npm install
npm run dev
```

Acesse http://localhost:3000. Na tela de login, escolha um perfil (Guilherme ou Fernando). Os dados ficam no localStorage do navegador.

## Conectar ao Supabase

1. Crie um projeto em https://supabase.com
2. Copie `.env.local.example` para `.env.local` e preencha `NEXT_PUBLIC_SUPABASE_URL` e `NEXT_PUBLIC_SUPABASE_ANON_KEY`.
3. No SQL Editor do Supabase, execute `supabase/migrations/001_init.sql`.
4. Crie os usuários (Guilherme e Fernando) em Authentication > Users, e insira os profiles correspondentes.
5. Rode `npm run dev`.

## Funcionalidades

- Dashboard com KPIs (MRR, clientes ativos, pipeline, tarefas, comissões)
- Leads (cadastro, busca, filtros, status)
- Pipeline Kanban (10 etapas do processo de vendas)
- Tarefas (pendentes/concluídas, prioridade)
- Agenda (eventos, demos, implantações)
- Propostas (geração a partir de deal, cálculo de valor)
- Comissões (10% vendas + 10% implantação após ativação)
- Territórios (progresso por praça)
- Parceiros (contadores, fornecedores, revendedores)
- Indicações (programa 1 mês grátis)
- Relatórios (funil, planos, conversão por origem, MRR acumulado)
- Configurações (backup JSON, import, dados de exemplo, reset)

## Estrutura

```
src/app/(dashboard)/   páginas do CRM
src/components/        UI e layout
src/lib/store.tsx      estado global (localStorage / demo)
src/lib/types.ts       tipos de domínio
supabase/migrations/   schema SQL
```