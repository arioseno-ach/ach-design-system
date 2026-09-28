# Input

## Purpose

Single-line text or numeric entry with a persistent label.

## Anatomy

1. Label (required, visible)
2. Field
3. Helper or error text (one slot)
4. Optional trailing icon (clear, visibility)

## Tokens

- Height: at least 44px (`foundations/accessibility.md`)
- Padding: `space.12`
- Radius: `radius.md`
- Border: `color.neutral.200`; focus `color.brand.500`; error `color.feedback.danger`
- Type: body / label from `foundations/typography.md`

## States

Empty, filled, focus, disabled, read-only, error.

## Rules

- Placeholder is an example, never the only label.
- Error text replaces helper text; do not show both.
- Associate label and error with the field (`for` / `aria-describedby`).
- Do not validate only on every keystroke in a way that blocks typing; prefer on blur or submit.
