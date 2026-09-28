# Stepper

## Purpose

Shows progress through a linear, finite sequence of steps. Used inside wizard-style templates.

## Anatomy

- Step list (number or indicator + short label)
- Current step highlighted
- Completed steps marked; upcoming steps muted

## Tokens

- Completed: `color.feedback.success` or `color.brand.500`
- Current: `color.brand.500`
- Upcoming: `color.neutral.400`
- Type: helper / caption for labels (`foundations/typography.md`)
- Gap: `space.8` / `space.12`

## States

Upcoming, current, completed, error (step needs attention).

## Rules

- Labels are short nouns or verb phrases (“Details”, “Review”), not sentences.
- Do not skip steps visually if the flow is linear; optional steps must be labeled optional.
- Stepper does not navigate by itself unless the template allows jumping to completed steps.
- Keep step count stable for a given flow; do not add/remove steps mid-session without explanation.
