# Cloudflare and R2

1. Add the domain to Cloudflare.
2. Create R2 buckets:
   - `livehelm-staging`
   - `livehelm-prod`
3. Location hint / jurisdiction: **European Union**.
4. Block public access.
5. Create an API token that can only read/write those buckets.
6. CORS: only the staging and production app origins.

## DNS later

When the app is on Vercel:

- `app.example.com` → production
- `staging.example.com` → staging

Apex can wait for a marketing site.
