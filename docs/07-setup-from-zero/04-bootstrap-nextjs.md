# Bootstrap Next.js

From the product repo root:

```bash
pnpm create next-app@latest . --ts --tailwind --eslint --app --src-dir=false --import-alias "@/*"
```

Then:

```bash
pnpm add drizzle-orm postgres zod @supabase/supabase-js @supabase/ssr
pnpm add -D drizzle-kit vite vitest @playwright/test
pnpm dlx shadcn@latest init
```

Add shadcn pieces only as needed: button, input, dialog, dropdown, sheet, tabs, badge, separator, tooltip, sonner.

## Folder seed

```text
app/
  (auth)/
  (app)/
  api/health/route.ts
components/ui/
lib/
  db/
  auth/
  permissions.ts
  audit.ts
drizzle/
  schema/
  migrations/
supabase/
  config.toml
  seed.sql
tests/
  unit/
  e2e/
  rls/
docs/          # this bible
```

## Scripts in package.json

```json
{
  "scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "next start",
    "lint": "next lint",
    "typecheck": "tsc --noEmit",
    "test": "vitest run",
    "test:e2e": "playwright test",
    "db:generate": "drizzle-kit generate",
    "db:migrate": "drizzle-kit migrate"
  }
}
```

## First UI rule

Create `components/ui` via shadcn. Do not create a parallel `components/Button.tsx`.
