# Incidents

## incidents

| Column | Type | Notes |
| --- | --- | --- |
| event_id | uuid | |
| public_id | text | INC-26-0142 |
| category | text | medical, security, fire, crowd, missing_person, lost_child, lost_property, assault, theft, welfare, weather, power, infrastructure, traffic, supplier, noise, other |
| priority | text | low, medium, high, critical |
| status | text | new, acknowledged, dispatched, on_scene, escalated, closed, cancelled |
| location_id | uuid null | |
| location_text | text null | if not on the map yet |
| summary | text | short |
| description | text | |
| reporter_name | text null | |
| reporter_user_id | uuid null | |
| assigned_team | text null | |
| assigned_person_id | uuid null | |
| restricted_detail | bool | security-sensitive body |
| sensitivity | text | normal, medical, security |
| reported_at | timestamptz | |
| acknowledged_at | timestamptz null | |
| dispatched_at | timestamptz null | |
| on_scene_at | timestamptz null | |
| closed_at | timestamptz null | |
| resolution | text null | |
| closing_notes | text null | |
| promoted_from_log_id | uuid null | |
| mutation_id | uuid null | |

Lost child and missing person are categories. Put extra fields in `incident_extras` jsonb only if needed: last seen, clothing. Keep them permissioned if they identify a child.

## incident_actions

| Column | Type | Notes |
| --- | --- | --- |
| incident_id | uuid | |
| at | timestamptz | |
| kind | text | reported, dispatched, arrived, ambulance_requested, ambulance_arrived, update, closed |
| body | text | |
| actor_user_id | uuid null | |

Example timeline is rows, not a rewritten description:

```text
14:37 reported
14:38 medical dispatched
14:39 security arrived
14:42 ambulance requested
14:49 ambulance arrived
15:02 closed
```

## medical_incident_extras

One-to-one, same incident_id. Permission `medical.read` / `medical.write`.

| Column | Type | Notes |
| --- | --- | --- |
| presenting_issue | text | short |
| team | text null | |
| treatment_summary | text null | operational, not a full record |
| ambulance_requested | bool | |
| ambulance_arrived_at | timestamptz null | |
| hospital_transfer | bool | |
| hospital_name | text null | |

Response times are derived from incident timestamps + extras.
