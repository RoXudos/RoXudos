# People

## people

| Column | Type | Notes |
| --- | --- | --- |
| event_id | uuid | |
| user_id | uuid null | |
| kind | text | employee, event_staff, volunteer, security, medical, steward, contractor, supplier, management, production, traffic |
| first_name | text | |
| last_name | text | |
| display_name | text | |
| role_title | text | |
| department | text | |
| phone | text null | |
| email | text null | |
| emergency_contact_name | text null | |
| emergency_contact_phone | text null | |
| assigned_location_id | uuid null | |
| supervisor_person_id | uuid null | |
| training_notes | text null | |
| status | text | expected, on_site, off_site, no_show |

Do not store DBS certificate numbers in FPR. A boolean `relevant_check_recorded` plus a file on a restricted attachment is enough until the safeguarding DPIA says more.

## shifts

| Column | Type | Notes |
| --- | --- | --- |
| person_id | uuid | |
| starts_at | timestamptz | |
| ends_at | timestamptz | |
| location_id | uuid null | |
| role_title | text null | |

## checkins

| Column | Type | Notes |
| --- | --- | --- |
| person_id | uuid | |
| type | text | in, out |
| at | timestamptz | |
| location_id | uuid null | |
| recorded_by | uuid | |

Staff-on-site count = people with latest checkin type `in` and not later `out`.
