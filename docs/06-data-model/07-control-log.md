# Control log

## control_log_entries

| Column | Type | Notes |
| --- | --- | --- |
| event_id | uuid | |
| public_id | text | LOG-26-0881 |
| at | timestamptz | default now |
| department | text | security, medical, production, traffic, control, welfare, other |
| message | text | Fight at Gate 3 |
| action | text null | Security dispatched |
| location_id | uuid null | |
| incident_id | uuid null | if promoted or linked |
| author_user_id | uuid | |
| time_adjusted | bool | true if not “now” |
| mutation_id | uuid null | |

No updates except a single “correct typo” within 5 minutes by the author, which is still audited and keeps the original in `before`. After 5 minutes, add a new line that references the old `public_id`.

This is the fastest write path in the product. Index `(event_id, at desc)`.
