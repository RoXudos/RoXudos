# Accounts to create

Create these in a password manager. Use the company email domain once it exists. Enable MFA on every admin login.

## Required before first production event

| Account | Plan hint | Region / setting |
| --- | --- | --- |
| Companies House + bank | n/a | UK |
| Domain registrar | n/a | — |
| Google Workspace or Microsoft 365 | Business starter | EU data if offered |
| 1Password or Bitwarden | Business | — |
| GitHub | Team (org) | Private repo |
| Supabase | Pro (PITR, extra project) | `eu-west-2` |
| Vercel | Pro | Link GitHub org |
| Cloudflare | Paid if you need support; free often enough | R2 EU |
| Resend or Postmark | Starter | |
| Sentry | Team | EU |
| Better Stack or Checkly | Starter | |

## Optional in FPR

| Account | Why |
| --- | --- |
| Maptiler / Mapbox | If OSM default tiles are not good enough |
| PostHog EU | Only if you truly need product analytics |
| Open-Meteo | No account if you only hit the public API within limits |

## Do not create yet

- AWS (unless a later decision)
- Twilio
- Stripe (manual invoices are fine)
- Intercom
- Native Apple / Google developer accounts (Phase B)

## Order

1. Password manager
2. Company email
3. GitHub org
4. Domain + Cloudflare DNS
5. Supabase
6. Vercel
7. R2
8. Email provider
9. Sentry
10. Uptime
