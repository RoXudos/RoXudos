# Tasks

## tasks

| Column | Type | Notes |
| --- | --- | --- |
| event_id | uuid | |
| public_id | text | TSK-26-0204 |
| title | text | Toilet block overflowing |
| details | text null | |
| priority | text | |
| status | text | open, in_progress, blocked, done, cancelled |
| assigned_team | text null | Facilities |
| assigned_person_id | uuid null | |
| location_id | uuid null | |
| due_at | timestamptz null | |
| completed_at | timestamptz null | |
| source_incident_id | uuid null | |
| mutation_id | uuid null | |

## task_comments

body, author, created_at.

Attachments via the files table.

Anything operational can become a task. The incident screen has “Create task”.
