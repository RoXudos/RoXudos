# Processors and DPAs

Every vendor that can see customer personal data needs:

1. a written DPA or equivalent
2. a named region
3. a reason they exist
4. an owner inside Livehelm
5. an off-boarding plan

## Intended FPR processor set

| Vendor | Purpose | Target region | Notes |
| --- | --- | --- | --- |
| Supabase | Postgres, auth, realtime | `eu-west-2` London | Confirm plan supports the region |
| Vercel | Web app hosting | Pin functions / project to EU if the product allows | Edge may still be global; document it |
| Cloudflare R2 | File uploads | EU jurisdiction bucket | Photos on incidents |
| Cloudflare DNS | DNS | Global | Usually not a data store of event records |
| Resend or Postmark | Transactional email | Prefer EU | Invites, alerts |
| Sentry | Errors | EU org | Scrub auth headers and PII |
| Better Stack or Checkly | Uptime | Document region | Synthetic checks only |
| Open-Meteo or weather API | Weather | No personal data if you only send lat/long of the site | Do not send staff names |
| GitHub | Source | US processor | Code, not event records. Still a vendor. |
| Google or Microsoft | Email / docs | Choose EU data if offered | Company email |

## Rules

- Do not add Intercom, Mixpanel, Google Analytics, or a US chatbot on the control-room app in FPR.
- Do not paste customer data into a personal ChatGPT session.
- If an AI coding tool is used, it must not receive production dumps.

## Customer-facing documents

Publish:

- subprocessor list with last-updated date
- DPA
- privacy policy

Update the list before a new processor sees production data, not after.
