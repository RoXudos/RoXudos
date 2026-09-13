# Deploy freeze

When any production event is `live`:

- No production deploys except severity-1 fixes.
- If you are a team of one, write the exception: what you shipped, why, and that you watched Sentry for an hour.
- Migrations that lock tables are forbidden during live.

Staging may continue.

Put a bot or a simple checklist: “events in status live” → warn the deployer.
