# Design tokens

Use shadcn/ui CSS variables. Do not invent a second token system.

## Recommended default (control room)

- Background: near-black or very dark slate
- Surface: slightly lighter slate
- Text: high-contrast off-white
- Muted text: grey that still passes contrast
- Accent: a single operational blue for focus and links
- No gradients

## Priority

| Priority | Word | Colour role |
| --- | --- | --- |
| Critical | CRITICAL | red |
| High | HIGH | orange |
| Medium | MEDIUM | amber |
| Low | LOW | grey/blue |

Never use colour alone.

## Status

| Status | Meaning |
| --- | --- |
| green | department coping |
| amber | stretched |
| red | overwhelmed / needs help |

These are **human-set** department statuses, not inferred by AI.

## Type

- UI: a standard readable sans already in shadcn (Inter or Geist)
- Tabular numbers for times and counts
- Do not use display serifs in the app

## Radius and shadow

Slight radius. Almost no shadow. This is not a card marketplace.

## Motion

100–150ms ease for drawers. No bounce. No confetti when an incident closes.
