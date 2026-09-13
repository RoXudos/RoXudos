# Logging and monitoring

## Application logs

Log:

- request id
- user id
- organisation id
- event id
- route
- status
- duration

Do not log:

- passwords
- tokens
- medical / safeguarding bodies
- full incident descriptions if you can avoid it
- file contents

## Monitoring

| Signal | Tool |
| --- | --- |
| Exceptions | Sentry EU |
| Uptime | Better Stack / Checkly on `/api/health` |
| Product lag | p95 of incident create |
| Realtime drop | client metric later |
| Disk / DB | Supabase dashboard + alerts on 80% |

## Alerts that wake a human

- Production down
- Error spike
- Auth error spike
- Backup failure
- Certificate failure

Do not wake a human for a single 404.
