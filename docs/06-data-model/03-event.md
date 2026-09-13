# Event

## events

| Column | Type | Notes |
| --- | --- | --- |
| organisation_id | uuid | |
| name | text | Festival 2026 |
| type | text | festival, pride, charity, … |
| status | text | draft, planned, build, live, closed, archived |
| timezone | text | IANA |
| venue_name | text null | |
| venue_address | text null | |
| expected_attendance | int null | |
| current_attendance | int null | manual in FPR |
| public_start_at | timestamptz null | |
| public_end_at | timestamptz null | |
| build_start_at | timestamptz null | |
| derig_end_at | timestamptz null | |
| module_flags | jsonb | `{ "safeguarding": true, "fundraising": false }` |
| cloned_from_event_id | uuid null | |
| medical_status | text | green/amber/red + set_by + note |
| security_status | text | same |

Department status may be a child table if you prefer history. FPR can start as columns plus audit on change.

## event_plans

File attachments tagged:

`event_management`, `emergency`, `security`, `medical`, `fire`, `traffic`, `crowd`, `accessibility`, `comms`, `weather`, `evacuation`, `other`

Structured plan editors are later.

## event_clone_jobs

| Column | Type | Notes |
| --- | --- | --- |
| source_event_id | uuid | |
| target_event_id | uuid | |
| copy_flags | jsonb | site, roles, playbooks, programme template, vendors |
| status | text | |

Never clone incidents, log, tasks, medical extras, safeguarding, or audit.
