# Weather and emergencies

## weather_snapshots

| Column | Type | Notes |
| --- | --- | --- |
| event_id | uuid | |
| observed_at | timestamptz | |
| temperature_c | numeric null | |
| rain_mm | numeric null | |
| wind_kph | numeric null | |
| wind_gust_kph | numeric null | |
| lightning | bool null | |
| visibility_m | numeric null | |
| warning_text | text null | |
| raw | jsonb | provider payload, no people |

Poll every 10 minutes while event is `build` or `live`.

## weather_thresholds

| Column | Type | Notes |
| --- | --- | --- |
| event_id | uuid | |
| metric | text | wind_kph, rain_mm, … |
| operator | text | gte, lte |
| value | numeric | |
| level | text | warning, critical |
| message | text | |

Crossing a threshold creates an `alerts` row. Do not auto-activate an emergency playbook.

## emergency_playbooks

| Column | Type | Notes |
| --- | --- | --- |
| event_id | uuid | or organisation template copied in |
| kind | text | fire, evacuation, severe_weather, major_medical, missing_child, security_threat, structural, power |
| title | text | |
| steps | jsonb | `[{ "order": 1, "text": "..." }]` |
| contacts | jsonb | `[{ "name", "role", "phone" }]` |

## emergency_activations

| Column | Type | Notes |
| --- | --- | --- |
| playbook_id | uuid | |
| activated_by | uuid | |
| activated_at | timestamptz | |
| stood_down_by | uuid null | |
| stood_down_at | timestamptz null | |
| notes | text null | |

Only humans with `emergency.activate`. Show a banner while `stood_down_at` is null.
