# Communications

## channels

| Column | Type | Notes |
| --- | --- | --- |
| event_id | uuid | |
| name | text | Event Control, Security, Medical, … |
| kind | text | department, custom |
| department | text null | |

Seed default channels when the event is created.

## messages

| Column | Type | Notes |
| --- | --- | --- |
| channel_id | uuid | |
| body | text | |
| priority | text | normal, high |
| author_user_id | uuid | |
| created_at | timestamptz | |

## message_reads

message_id, user_id, read_at.

## alerts

| Column | Type | Notes |
| --- | --- | --- |
| event_id | uuid | |
| title | text | |
| body | text | |
| level | text | info, warning, critical |
| source | text | user, weather, emergency, system |
| created_by | uuid null | |
| expires_at | timestamptz null | |

Alerts appear on Live and in the bell.

Public emergency notifications are Phase F. Do not add SMS fields now.
