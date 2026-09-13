# Alternatives considered

| Option | Verdict | When to revisit |
| --- | --- | --- |
| Next.js + own Nest/Fastify API + RDS | Rejected for FPR | When mobile + workers need a standalone API, or a customer forbids Supabase |
| Clerk / Auth0 | Rejected | Extra US SaaS in the auth path. Supabase Auth is enough |
| Better Auth + Neon + custom websocket | Good, more work | If we leave Supabase |
| Firebase | Rejected | Weak relational model, weaker GDPR story |
| MongoDB | Rejected | Incidents, permissions, and audit are relational |
| Prisma | Rejected | Drizzle is lighter and closer to SQL |
| AWS ECS + RDS + Cognito from day one | Rejected as default | Valid enterprise later |
| Kubernetes | Rejected | No |
| Native-only mobile first | Rejected | Founder chose desktop first |
| Leaflet only | Acceptable fallback | If MapLibre is painful. Prefer MapLibre |
| Socket.io on a custom server | Rejected for FPR | Supabase Realtime exists |
| GraphQL / Hasura | Rejected | Extra layer, easy to leak fields |

## Exit hatch from Supabase

If you must leave:

1. Postgres dump / logical replication to RDS or Neon in `eu-west-2`
2. Replace auth with Better Auth using the same `auth.users` IDs
3. Replace realtime with a small fan-out worker
4. Keep Drizzle schema as the source of truth

Design tables as ordinary Postgres, not as Supabase-only magic, and the exit stays cheap.
