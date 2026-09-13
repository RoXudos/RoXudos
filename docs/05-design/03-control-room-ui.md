# Control room UI

This is the centrepiece. Optimise for a large screen. It must still work on a 1280px laptop.

## Layout (large screen)

```text
┌ Header: EVENT NAME  LIVE   19:41  Alerts  User ─┐
│ ATT 8421   STAFF 287   INC 4   CRIT 1   TASK 23 │
│ MED: amber   SEC: green   WX: wind warn         │
├───────────────┬────────────────┬────────────────┤
│ Active        │ NOW / NEXT     │ Control log    │
│ incidents     │ LATER          │                │
│               │                │                │
│               ├────────────────┤                │
│ Open critical │ Mini map       │ Quick log      │
│ tasks         │                │                │
└───────────────┴────────────────┴────────────────┘
```

Numbers are examples, not seed fiction in production.

## Tiles

- Attendance (manually updated in FPR, later import)
- Staff currently checked in
- Active incidents
- Critical incidents
- Open tasks
- Medical status (manager-set: green / amber / red + one line)
- Security status (same)
- Weather (temp, wind, rain, warning)
- Current programme
- Next programme item

## Active incidents list

Each row:

```text
14:37  MEDICAL   Main Stage   HIGH   INC-26-0142
14:42  CROWD     Gate 2       MEDIUM INC-26-0143
```

Click opens the incident. No hover-only information.

## Programme

```text
NOW   DJ Example
NEXT  Example Band
19:30 Headliner
```

Changes must appear immediately for authorised users.

## Quick log

Always visible on Live. One compact composer. Success = new line at the top of the stream.

## Density

This screen is a workstation, not a landing page. Reduce padding until it breathes but still shows the last ten log lines without scrolling on a 27-inch monitor.

## What not to put on Live

- Vendor insurance PDFs
- Safeguarding case titles
- Billing
- Long biography of the artist
- AI chat drawer
