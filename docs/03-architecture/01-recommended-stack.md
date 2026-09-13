# Recommended stack

This is the locked stack (decision D004–D007, D019, D020).

## Application

| Layer | Choice |
| --- | --- |
| Language | TypeScript, strict |
| App | Next.js App Router |
| UI | Tailwind CSS + shadcn/ui |
| Validation | Zod |
| Server data | Next.js server actions / route handlers |
| Client cache | TanStack Query where the screen is live |
| Package manager | pnpm |
| Tests | Vitest + Playwright |

## Data and auth

| Layer | Choice |
| --- | --- |
| Database | PostgreSQL 16 on Supabase, region `eu-west-2` |
| Access | Drizzle ORM + Supabase RLS |
| Auth | Supabase Auth (email + MFA). Passkeys can come later |
| Realtime | Supabase Realtime on operational tables |
| Migrations | Drizzle kit, committed to git |

## Hosting and files

| Layer | Choice |
| --- | --- |
| Web | Vercel, linked to `staging` and `production` |
| Files | Cloudflare R2, EU bucket, private objects |
| DNS | Cloudflare |
| Email | Resend or Postmark, transactional only |
| Errors | Sentry EU |
| Uptime | Better Stack or Checkly |
| Weather | Open-Meteo first (site coordinates only) |
| Maps | MapLibre GL, GeoJSON overlays, OSM or your own tiles |

## Why not a custom Node API on day one

The control room is a single web app with a Postgres brain. Next.js + RLS is enough for FPR. Extract a separate API when a native mobile client or a worker fleet needs it — Phase B is the likely moment.

## Repository shape on day one

```text
livehelm/
  app/
  components/
  lib/
  drizzle/
  supabase/
  docs/
  tests/
```

## Versions

Pin current LTS / stable releases when you bootstrap. Do not chase nightly Next.js.

## Things that are not in the stack

- GraphQL
- Prisma (use Drizzle)
- Clerk / Auth0
- MongoDB
- Firebase
- Tailwind UI marketing templates
- A second CSS framework
- Kubernetes
- AWS account on day one
