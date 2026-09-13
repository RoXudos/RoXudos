# Env and secrets

Use these names everywhere. No `API_KEY` soup.

```text
NEXT_PUBLIC_APP_URL=
NEXT_PUBLIC_SUPABASE_URL=
NEXT_PUBLIC_SUPABASE_ANON_KEY=

SUPABASE_SERVICE_ROLE_KEY=
DATABASE_URL=                 # postgres connection for Drizzle/migrations
DIRECT_URL=                   # if pooled vs direct needed

R2_ACCOUNT_ID=
R2_ACCESS_KEY_ID=
R2_SECRET_ACCESS_KEY=
R2_BUCKET=
R2_ENDPOINT=

SENTRY_DSN=
SENTRY_ENVIRONMENT=

EMAIL_PROVIDER=resend
EMAIL_API_KEY=
EMAIL_FROM=

WEATHER_LAT=
WEATHER_LNG=
# or per-event coordinates stored in DB; env only for demo

CRON_SECRET=
```

## Files

- `.env.example` committed with empty values and comments
- `.env.local` never committed
- Vercel + GitHub Environment stores the real values

## Rotation

If any secret is pasted into chat, rotate it. Treat Slack/WhatsApp as public.
