# Data residency and transfers

## Default

All customer event data is stored in **London (`eu-west-2`)** for Postgres and in an **EU R2 bucket** for files.

This is the simplest way to serve UK + EU seriously and still accept US organisations.

## What “US from the start” means

US organisations may subscribe. Their data still lives in London unless a later **organisation region** feature ships.

Document that in the DPA and the sales call.

## Later region feature (not FPR)

`organisation.region = eu_west_2 | us_east_1`

Only build this when a customer pays for it. It doubles operational cost.

## Transfers that still happen

- A UK founder supporting a customer from a laptop
- GitHub for source
- Email delivery
- Error reports (scrubbed)

List them. Do not pretend the only copy of data is the database.

## Backups

Backups stay in the same political region as the primary database. Do not “just tick US backup” for convenience.
