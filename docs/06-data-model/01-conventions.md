# Conventions

## Keys

- Internal primary key: `uuid`. Generate in the database (`gen_random_uuid()`).
- Public operator ID: separate `public_id` text, unique per event where relevant.

## Tenancy

- Never create an operational table without `organisation_id`.
- Event-scoped rows must have both `organisation_id` and `event_id`.
- Check that `event.organisation_id` matches the row’s `organisation_id` in a constraint or trigger.

## Soft delete

Do not hard-delete incidents, log lines, tasks, safeguarding cases, or audit.

Use:

- `cancelled` / `closed` statuses for operational records
- `revoked` for credentials
- Hard delete only for draft files that never confirmed upload

## Enums

Prefer Postgres enums or check constraints for:

- event_status, incident_status, task_status, priority, department

Keep a text `other` / `notes` only where the brief needs it.

## JSON

Allowed for:

- GeoJSON geometry
- audit before/after
- module_flags
- playbook steps

Not allowed as a junk drawer for fields you will filter on next week. Those become columns.

## mutation_id

All user writes accept an optional `mutation_id uuid`. Unique per organisation. Enables later offline retry.

## People vs users

A `person` is someone on the event. A `user` is someone who can sign in. Link them with `person.user_id` nullable.
