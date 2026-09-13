# Email, errors, uptime

## Email

Resend or Postmark:

- Domain authentication (SPF, DKIM, DMARC)
- From: `Livehelm <noreply@yourdomain.com>`
- Templates: invite, reset, “you were added to an event”

Do not send operational incident SMS in FPR.

## Sentry

- Create an EU organisation
- Project: `livehelm-web`
- Environments: `local`, `staging`, `production`
- Turn on session replay only if you can scrub PII. Default **off** for FPR.
- `beforeSend` strip cookies and authorization

## Uptime

Probe:

```text
GET https://app.yourdomain.com/api/health
GET https://staging.yourdomain.com/api/health
```

Alert to `ops@` and a phone if you are the only operator.

Health must check: app process up, can SELECT 1 from Postgres. Do not check every table.
