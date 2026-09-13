# Schema and RLS

## Steps

1. Create Drizzle schemas for `organisations`, `profiles`, `organisation_memberships`, `events`, `event_memberships`, `invites`, `audit_events`, `event_sequences`.
2. Generate a migration.
3. Apply to local Supabase.
4. Enable RLS on every table.
5. Write policies:

```text
A user can read an organisation if they have an active membership.
A user can read events of that organisation.
A user can write events if they have event.create / event.update.
Service role bypasses RLS for migrations only.
```

6. Add a SQL helper `current_user_org_ids()` that reads memberships for `auth.uid()`.
7. Repeat the helper pattern for event IDs.

## Pitfalls

- Policies that use `auth.uid()` on a join without an index will be slow. Index `user_id` on membership tables.
- Do not disable RLS to “get the demo working”.
- `audit_events` is insert-only for normal roles. No update/delete policies for customers.

## Done when

A second local user in a second org cannot `select` the first org’s events via the SQL editor using that user’s JWT.
