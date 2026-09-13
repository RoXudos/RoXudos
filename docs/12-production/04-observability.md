# Observability

Must be green before go-live:

| Check | Owner |
| --- | --- |
| `/api/health` prod | uptime tool → phone |
| `/api/health` staging | same, lower priority |
| Sentry error spike | email + Slack/email |
| Supabase disk / connection | dashboard alert |
| Certificate expiry | Cloudflare / Vercel |
| Cron weather | Sentry on failure |
| Backup | confirm in vendor UI |

Weekly: look at Sentry. Monthly: look at cost so a runaway realtime bill is seen.
