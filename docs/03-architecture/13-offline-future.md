# Offline future

Not in FPR. Design hooks so Phase C is not a rewrite.

## Hooks to leave now

- Every write has a client-generated `mutation_id` (UUID) so a later queue can retry without duplicates.
- File uploads already go through an explicit confirm step.
- Map GeoJSON can be cached as a single authorised blob.
- Do not pretend a record is saved until the server acknowledges it.

## Honest UI

Even in FPR, if a write fails, say it failed. Never show a green tick on a log line that never reached Postgres.

## Later model

```text
local draft → queue → sync → conflict
```

Conflict rule to decide in Phase C:

- Incidents: first server version wins; late field edits become timeline comments.
- Control log: append-only, so retries with the same `mutation_id` are idempotent.

Do not implement the queue now. Do implement `mutation_id` on writes now. It is cheap.
