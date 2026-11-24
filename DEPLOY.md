# Deploy — CRM Aptto (domínio gratuito)

## Opção 1 — Netlify Drop (mais rápido, sem conta)
1. Acesse https://app.netlify.com/drop
2. Arraste a pasta `out/` (ou o arquivo `crm-aptto-static.zip` descompactado)
3. O Netlify gera um link gratuito `https://<nome-aleatorio>.netlify.app`
4. (Opcional) Crie conta gratuita e renomeie o site para `crm-aptto.netlify.app`

## Opção 2 — Vercel (domínio .vercel.app)
1. Suba a pasta `crm-aptto` para um repositório GitHub próprio
2. Acesse https://vercel.com → "New Project" → importe o repo
3. Vercel detecta Next.js automaticamente e publica em `https://crm-aptto.vercel.app`
4. Para modo com Supabase: adicione as env vars no painel da Vercel e renomeie `src/proxy.ts.example` → `src/proxy.ts`, remova `output: "export"` do next.config.ts

## Opção 3 — GitHub Pages
1. Crie repo e publique a pasta `out/` na branch `gh-pages`
2. Ative GitHub Pages nas settings do repo
3. Acesse `https://<usuario>.github.io/<repo>/`

## Voltar para modo dinâmico (com Supabase)
1. Edite `next.config.ts`: remova `output: "export"`, `trailingSlash`, `images.unoptimized`
2. Renomeie `src/proxy.ts.example` → `src/proxy.ts`
3. Configure `.env.local` com as credenciais do Supabase
4. `npm run build` (sem export estático)