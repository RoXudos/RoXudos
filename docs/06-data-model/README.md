# 06 — Data model

All first-production tables are sketched here. Implement them as Drizzle schema plus RLS. Do not invent a second naming scheme.

Every tenant table includes:

```text
id              uuid pk
organisation_id uuid not null
created_at      timestamptz not null
updated_at      timestamptz not null
created_by      uuid null
updated_by      uuid null
```

Event-scoped tables also include `event_id`.

| File | Entities |
| --- | --- |
| [01-conventions.md](01-conventions.md) | Types, nullability, soft delete |
| [02-identity.md](02-identity.md) | Org, user, membership, roles |
| [03-event.md](03-event.md) | Event, modules, status, clone |
| [04-site.md](04-site.md) | Map, zone, location |
| [05-people.md](05-people.md) | Person, shift, check-in |
| [06-incidents.md](06-incidents.md) | Incident, actions, medical extras |
| [07-control-log.md](07-control-log.md) | Log lines |
| [08-tasks.md](08-tasks.md) | Tasks |
| [09-programme.md](09-programme.md) | Stages and items |
| [10-comms.md](10-comms.md) | Channels, messages, alerts |
| [11-weather-and-emergencies.md](11-weather-and-emergencies.md) | Weather snapshots, playbooks |
| [12-credentials-and-vendors.md](12-credentials-and-vendors.md) | Passes and documents |
| [13-safeguarding.md](13-safeguarding.md) | Restricted cases |
| [14-audit-and-files.md](14-audit-and-files.md) | Audit, files, sequences |
| [15-reporting.md](15-reporting.md) | Generated reports |
