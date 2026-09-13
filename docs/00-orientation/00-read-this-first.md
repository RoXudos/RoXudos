# Read this first

Livehelm is not a ticketing system and not an event-planning calendar.

It is an operational platform for people who plan, control, run, and review live events.

The product exists because event control work is still often split across spreadsheets, WhatsApp, paper forms, radio logs, and disconnected tools. The job of this platform is to give organisers and event-control teams a single operational picture.

## The question the product must answer

At any moment, an authorised person should be able to answer:

- What is happening?
- Where is it happening?
- Who is dealing with it?
- What needs doing?
- What has already happened?
- What is happening next?
- Who is responsible?
- What risks currently exist?
- What incidents are active?
- What tasks remain outstanding?

If a screen does not help answer one of those questions, it is probably the wrong screen.

## The lifecycle

```text
PLAN → BUILD → BRIEF → OPERATE → RESPOND → CLOSE → REVIEW
```

The centre of the product is **live event control**. Planning modules exist to make live control accurate. Reporting modules exist so the next event is better than the last one.

## Who uses it, and in what conditions

Users may be:

- standing in event control
- walking a festival site
- using a laptop, a large control-room screen, a tablet, or later a phone
- working under pressure
- dealing with an emergency
- working with poor connectivity

The first production release is **desktop and large-screen control room first**. Field mobile comes later. Design the desktop product so a later mobile app can reuse the same APIs and permissions.

## What “production-grade from day one” means here

It does not mean build every module before any event uses the system.

It does mean:

- real authentication
- real tenant isolation
- real RBAC
- real audit logs
- staging and production
- backups you have restored at least once
- monitoring and alerting
- written privacy / processor contracts
- no fake operational data in the live product

A thin demo with mocked incidents is not Livehelm.

## What not to do

- Do not turn this into an enterprise maze. Power must stay simple.
- Do not let AI close incidents, dispatch resources, or declare emergencies.
- Do not put medical or safeguarding data on a general dashboard.
- Do not build the application inside the GitHub profile repository.
- Do not start with native apps, offline sync, or a public crowd app.
- Do not add ticketing, CRM, or marketing automation because they are common SaaS extras.

## The only test that matters

> Would this actually help someone running a live event?

If the answer is no, do not build it yet.
