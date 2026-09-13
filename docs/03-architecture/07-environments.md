# Environments

Production-grade from day one means **three** environments, not one laptop.

| Name | Purpose | Data |
| --- | --- | --- |
| Local | Develop | Fake org, fake event, no real people |
| Staging | Rehearse releases and training | Synthetic or consented dummy data only |
| Production | Real events | Real data, locked down |

## Rules

- Separate Supabase projects for staging and production.
- Separate Vercel environments.
- Separate R2 buckets.
- Separate Sentry environments.
- No production credentials on developer laptops in env files that get committed.
- Preview deployments may use staging, never production.

## Promotion path

```text
branch → PR → CI → deploy preview / staging → migrate staging → smoke test → deploy production → migrate production
```

Migrations run as part of the release, not by hand on a Friday of a live event.

## Freeze

When a customer event is `live`, production deploys require two humans or a written exception. Put this in the production runbook even if the team is one person — the second human can be a contractor or a written “I accept the risk” note.

## Seed data

Local and staging get:

- One demo organisation
- One festival-shaped event
- One charity-shaped event
- Users for each major role
- A small map and programme
- A handful of incidents and log lines

Never seed production with demo incidents.
