# Audit log

## Record shape

| Field | Required |
| --- | --- |
| id | yes |
| organisation_id | yes |
| event_id | when applicable |
| actor_user_id | yes, or `system` |
| action | yes (`incident.update`) |
| record_type | yes |
| record_id | yes |
| before | jsonb, nullable |
| after | jsonb, nullable |
| ip | if available |
| user_agent | if available |
| created_at | yes, UTC |

## Must audit

- All creates/updates/status changes on incidents, tasks, log (log is itself evidence; still audit edits)
- Assignment
- Emergency activate / stand-down
- Role changes and invites
- Restricted reads (medical, safeguarding)
- Exports
- File upload / delete
- Event clone
- Attendance figure changes
- Threshold changes
- Support break-glass

## Must not

- Silently edit an old audit row
- Delete audit rows from the app
- Store passwords or MFA secrets in `before`/`after`

## Retention

Keep audit at least as long as the event operational record. Default: 7 years or until the customer contract says otherwise. Confirm with counsel.

## UI

Filterable by actor, record, day. Exportable by Organisation Owner and Event Director. Not editable.
