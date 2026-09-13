# Production down

1. Check Vercel status and project deployments.
2. Check Supabase status and project health.
3. Hit `/api/health`.
4. If DB is down: customer cannot log. Tell them to paper/radio log with timestamps; you will not invent catch-up.
5. Communicate on the status page and to the live event contact.
6. Do not “quickly migrate” without a second thought.
7. After restore: confirm the last log line time with the customer. Offer a late-entry window.

If the app is down, event control still runs the event. The runbook is honesty plus recovery, not heroics.
