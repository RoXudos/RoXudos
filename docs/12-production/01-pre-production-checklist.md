# Pre-production checklist

Do not put a real organisation’s staff list on production until this is green.

## Company and legal

- [ ] UK company and bank
- [ ] Domain and `privacy@` / `security@` / `support@`
- [ ] ICO registration
- [ ] Privacy policy, terms, DPA, subprocessor list published
- [ ] Processor DPAs signed (Supabase, Vercel, Cloudflare, email, Sentry)
- [ ] DPIA signed if medical or safeguarding will be on
- [ ] Cyber / PI insurance discussed with a broker

## Platform

- [ ] Dedicated product repo, not the profile repo
- [ ] Staging and production isolated
- [ ] RLS tests passing in CI
- [ ] MFA enforced on privileged roles
- [ ] Backups: restore drill done
- [ ] Sentry + uptime alerting to a human
- [ ] Rate limits on login and log/incident create
- [ ] Security headers
- [ ] No production seed incidents
- [ ] Service role key not in the browser
- [ ] R2 buckets private

## Product

- [ ] Slice gates 1, 2–4, and 5–7 complete for the modules you will actually enable
- [ ] A stranger can file a log line from the one-page briefing
- [ ] Cross-tenant test run on staging the day before go-live
