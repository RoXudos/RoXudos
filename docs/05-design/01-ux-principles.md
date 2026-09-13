# UX principles

The product should feel professional, modern, fast, operational, calm, clear, and reliable.

## Do

- Prioritise information hierarchy and speed
- Use words operators already say: incident, log, gate, dispatch
- Put the next action near the thing it affects
- Prefer one dense control-room screen over five marketing cards
- Make the primary action obvious: **Log**, **Incident**, **Task**
- Timestamp by default
- Use priority **words** plus colour

## Do not

- Excessive gradients
- Overly rounded cards everywhere
- Huge marketing typography on operational screens
- Fake-looking AI interfaces
- Unnecessary animation
- Clutter
- Over-engineering
- Rainbow dashboards
- Dark mode as a science project before the light (or dark) control-room theme is readable. Pick **one** default for FPR: a dark, low-glare control room theme is acceptable if contrast is proven. Do not ship two unfinished themes.

## Form rule

If a control operator is standing up and someone is shouting a radio message, the form is too long.

Control log fields:

1. Department (segmented, last used remembered)
2. Message
3. Action (optional but encouraged)
4. Location (optional, typeahead)

Time is now unless they expand “adjust time”.

## Language

British English in the product by default (`organise`, `licence` as a noun in vendor docs). US customers can later get a locale. Do not mix `canceled` and `cancelled`.
