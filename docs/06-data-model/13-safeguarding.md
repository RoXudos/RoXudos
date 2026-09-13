# Safeguarding

## safeguarding_cases

| Column | Type | Notes |
| --- | --- | --- |
| event_id | uuid | |
| public_id | text | SG-26-0011 |
| status | text | open, escalated, closed |
| summary | text | restricted |
| details | text | restricted |
| location_id | uuid null | |
| contacts | jsonb | internal contacts only |
| assigned_user_id | uuid null | |
| opened_at | timestamptz | |
| closed_at | timestamptz null | |

RLS: only users with `safeguarding.read`.

Audit **every select** of `details` (application-level, because Postgres does not log row reads by default unless you add a function wrapper).

## safeguarding_events

Timeline on the case: note, escalation, referral, close.

No map pin. No inclusion in the open incident wall.

Training / check flags live on `people` as booleans, not copies of certificate numbers.
