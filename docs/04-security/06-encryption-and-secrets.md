# Encryption and secrets

## In transit

TLS everywhere. HSTS on the production domain.

## At rest

- Supabase / AWS volume encryption on
- R2 encryption on
- No extra application-level field encryption in FPR except if counsel requires it for medical notes. If you add it later, you must still search/assign carefully.

## Secrets

- Vercel env + Supabase vault / GitHub Environments
- Rotate on staff off-boarding
- Never commit `.env`
- Different keys per environment
- Service role key **never** shipped to the browser

## Client keys

The browser may have the Supabase anon key **only** if RLS is complete and tested. Prefer server-side Supabase client with the user session for writes.

Recommendation: **server-side only** for writes in FPR. Browser uses the Next.js app. Realtime can use a short-lived token scoped to the event.
