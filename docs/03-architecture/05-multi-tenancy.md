# Multi-tenancy

## Model

One **organisation** has many **events**.

Users belong to an organisation. They may also have **event-scoped roles**.

```text
ABC Events Ltd
  Festival 2026
  Christmas Market 2026
  Pride 2027
```

## Isolation rule

There is no cross-organisation read. Not in search, not in analytics, not in error logs, not in AI later.

Every operational table has `organisation_id`.

Event-scoped tables also have `event_id`.

## RLS pattern

```sql
-- pseudocode
using (organisation_id = current_org_id())
with check (organisation_id = current_org_id())
```

`current_org_id()` comes from a JWT claim or a `security definer` helper that reads membership.

Never rely on “we always remember the where clause in the app”.

## Platform admin

A Livehelm staff role exists **outside** customer organisations for support.

Rules:

- Break-glass only
- Every access audited
- No standing production query access from laptops without SSO + reason

Do not implement a hidden back door that skips RLS in the customer app.

## Shared reference data

Incident categories, default playbooks, and location types can be global seed tables with no personal data.

Customer edits are copied into the organisation or event, not written over the global seed.
