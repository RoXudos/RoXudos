# Reporting

## event_reports

| Column | Type | Notes |
| --- | --- | --- |
| event_id | uuid | |
| generated_at | timestamptz | |
| generated_by | uuid | |
| payload | jsonb | counts and timelines |
| lessons_learned | text null | human |
| file_id | uuid null | PDF snapshot |

Generate from queries, do not type counts by hand.

FPR payload includes:

- attendance (target vs last entered)
- staff numbers / peak on site
- incident counts by category, priority, status
- medical extras counts (if exporter permitted)
- lost child / lost property counts
- ambulance / hospital counts (if permitted)
- task counts and overdue
- emergency activations
- control-log volume
- timeline of critical incidents
- weather threshold alerts

Omit safeguarding narratives. Counts of cases only, and only to permitted roles.

## debrief (later)

Phase D table: department, went_well, went_wrong, change, fix_before_next. Not FPR-blocking if the report has a single lessons-learned field.
