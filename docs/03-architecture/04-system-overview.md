# System overview

```text
Browser (control room desktop)
        |
        | HTTPS
        v
Next.js on Vercel
        |                          |
        | user session             | signed URL
        v                          v
Supabase Auth + Postgres RLS     Cloudflare R2
        |
        | realtime channel
        v
Browser live widgets
```

## Request path for a write

1. User submits “create control log”.
2. Next.js verifies session.
3. Server checks event membership and permission `control_log.create`.
4. Zod validates payload.
5. Insert row with `organisation_id`, `event_id`, `created_by`, UTC timestamps.
6. Trigger / application writes audit row.
7. Realtime notifies other control-room clients on that event channel.
8. UI prepends the line. If realtime fails, a refresh still shows the row.

## Trust boundaries

- The browser is not trusted.
- RLS is trusted.
- Permission checks in Next.js are trusted and must match RLS.
- Object storage is not public. Only short-lived signed URLs.

## Core bounded contexts

- Identity (org, user, membership, roles)
- Event (event, modules, status)
- Site (map, zone, location)
- People (person, shift, check-in)
- Operate (log, incident, task, programme, message, alert)
- Sensitive (medical extras, safeguarding case)
- Compliance (vendor document, credential)
- Evidence (audit, report)

Keep module folders aligned to those names.
