# Weather

## Steps

1. Store site coordinates on the site row.
2. Cron (Vercel cron + `CRON_SECRET`) every 10 minutes for events in `build` or `live`.
3. Fetch Open-Meteo (or paid) using only lat/lng.
4. Save snapshot.
5. Live tile reads latest snapshot.
6. Thresholds UI for Event Control Manager.
7. Crossing creates an alert. It does **not** activate an emergency.

## Failure

Tile says “Weather unavailable”. Cron errors go to Sentry.

## Done when

A wind threshold of 40 kph creates an alert when a snapshot exceeds it (you can test by inserting a fake snapshot in staging).
