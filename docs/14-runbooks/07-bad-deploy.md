# Bad deploy

1. Instant rollback on Vercel to previous successful deployment.
2. If a migration applied: decide forward-fix vs restore. Table locks during a live event are a last resort.
3. Tell the live customer if writes failed.
4. Postmortem even if you are a team of one. Half a page is enough.
