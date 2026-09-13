# Accessibility

This is software used under stress. Accessibility is not a polish pass.

## FPR bar

- Keyboard all primary flows
- Visible focus
- Contrast AA for text and priority labels
- Form labels, not placeholder-only
- Errors associated with fields
- Live region for new critical incidents and emergency banners (`aria-live=assertive` for emergency, `polite` for new log lines if it does not shout constantly)
- Do not auto-play sound without a setting. A short optional chime for critical / emergency is allowed, default off until the control manager turns it on
- Map has a list alternative
- Reduced-motion respected

## Event accessibility (the domain module)

Separate from UI a11y. Organisers record site accessibility assets: step-free routes, accessible toilets, viewing platforms, quiet areas, BSL, hearing loops, assistance dogs, accessible parking, shuttles.

That module’s fields are in the data model. The app itself must still be usable by disabled control staff.

## Language

Plain English. Avoid idioms on emergency playbooks.
