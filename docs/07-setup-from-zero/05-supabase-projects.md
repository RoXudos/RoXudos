# Supabase projects

Create **three** projects if budget allows, minimum **two** (local + production) and add staging as soon as the Pro plan allows.

| Project | Name | Region |
| --- | --- | --- |
| Local | `supabase start` | your machine |
| Staging | `livehelm-staging` | eu-west-2 |
| Production | `livehelm-prod` | eu-west-2 |

## On each hosted project

- [ ] Region London
- [ ] Point-in-time recovery on (Pro)
- [ ] Email auth enabled
- [ ] MFA enabled
- [ ] Confirm signup disabled (invite only)
- [ ] Leaked password protection on
- [ ] PostGIS extension on
- [ ] `pgcrypto` on
- [ ] Network restrictions later if you need them

## Local

```bash
pnpm dlx supabase login
pnpm dlx supabase init
pnpm dlx supabase start
```

Link staging and production separately. Never link local blindly to prod.

## RLS

Enable RLS on every public table as you create it. An empty table with RLS on and no policy is safer than a table with RLS off.

## Service role

Store `SUPABASE_SERVICE_ROLE_KEY` only on the server. If it leaks, rotate immediately and audit.
