# Decisions log

This file is binding until a newer dated entry replaces a row.

If you want to change a locked decision, add a new entry. Do not silently edit history.

## Locked decisions

| ID | Date | Decision | Choice | Why |
| --- | --- | --- | --- | --- |
| D001 | 2026-09-13 | Audience | Project bible for founder, developers, hired team, and AI agents | One source of truth |
| D002 | 2026-09-13 | Doc structure | Master index plus deep phase folders | Long project, many readers |
| D003 | 2026-09-13 | Product repo | New private repo. Not the GitHub profile repo | Profile README and product engineering must stay separate |
| D004 | 2026-09-13 | Stack | Next.js + TypeScript + PostgreSQL + Supabase (eu-west-2) + Vercel + Cloudflare R2 + MapLibre | Simplest UK-friendly production path that still supports RLS, realtime, and files |
| D005 | 2026-09-13 | Auth | Supabase Auth for first production, with a documented exit | Fastest path to sessions, MFA, and RLS. Revisit if a US-only auth requirement appears |
| D006 | 2026-09-13 | ORM | Drizzle ORM against Postgres, plus Supabase client for auth/realtime/storage | Typed schema and migrations without abandoning Supabase features |
| D007 | 2026-09-13 | Hosting | Vercel for the web app, Supabase in London, R2 in EU | Production-grade without standing up AWS on day one |
| D008 | 2026-09-13 | Data residency default | Primary region London (`eu-west-2`). Organisation data stays in the EU/UK region unless a later residency feature ships | UK + EU baseline; US customers accepted under a transfer mechanism, not by defaulting the database to the US |
| D009 | 2026-09-13 | Year-one ops | Staging + production, PITR backups, monitoring, error tracking, uptime from day one | Founder chose production-grade infrastructure |
| D010 | 2026-09-13 | First ship scope | Wider first production release, desktop control room first | Founder chose a larger first ship than the original 12-item MVP |
| D011 | 2026-09-13 | Mobile | Desktop / large-screen first. Field mobile is a later phase | Control room is the differentiator |
| D012 | 2026-09-13 | Maps | Interactive site map in the first live-control version | Founder chose map in v1 |
| D013 | 2026-09-13 | Event types | Generic platform with module flags per type | One codebase, not one app per event type |
| D014 | 2026-09-13 | Markets | UK + EU + US legally supported from the start | Privacy programme must not be UK-only |
| D015 | 2026-09-13 | Company setup | From zero, UK company first | No existing company/domain/analytics stack |
| D016 | 2026-09-13 | Working name | Livehelm | Temporary, pending clearance |
| D017 | 2026-09-13 | AI | No autonomous emergency or incident decisions. AI is later and read-only over authorised data | Safety and liability |
| D018 | 2026-09-13 | History | Operational history is append-only. Corrections are new entries | Event control evidence |
| D019 | 2026-09-13 | Package manager | `pnpm` | Fast, strict, good enough for later workspaces |
| D020 | 2026-09-13 | UI kit | Tailwind CSS + shadcn/ui, calm operational theme | Reuse, not a custom design system on day one |

## How to add a decision

Copy this block to the bottom of the locked table, increment the ID, and never reuse an ID.

```text
| D0XX | YYYY-MM-DD | Topic | Choice | Why |
```

If a decision reverses an older one, keep the old row and add:

```text
| D0XX | YYYY-MM-DD | Replaces D0YY | New choice | Why the old choice is no longer right |
```
