# Audit, files, sequences

## audit_events

See [../04-security/05-audit-log.md](../04-security/05-audit-log.md).

Indexes: `(organisation_id, created_at desc)`, `(record_type, record_id)`.

## files

| Column | Type | Notes |
| --- | --- | --- |
| organisation_id | uuid | |
| event_id | uuid null | |
| parent_type | text | |
| parent_id | uuid | |
| bucket_key | text | |
| mime | text | |
| size_bytes | int | |
| status | text | pending, ready, rejected |
| sensitivity | text | inherits parent |

## event_sequences

| Column | Type | Notes |
| --- | --- | --- |
| event_id | uuid | |
| kind | text | incident, log, task, safeguarding, credential |
| next_value | int | increment in a transaction |

Used to mint `INC-26-0142`.
