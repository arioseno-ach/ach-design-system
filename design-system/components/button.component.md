# Button

## Purpose

Triggers a single action. One primary button per view.

## Variants

| Variant | Use |
| --- | --- |
| Primary | The main forward action |
| Secondary | Supporting action |
| Tertiary / text | Low emphasis, navigation-like |
| Destructive | Irreversible or harmful action; confirm with dialog |

## Anatomy

Label (required). Optional leading or trailing icon. No dual competing labels.

## Tokens

- Radius: `radius.md`
- Padding: `space.12` vertical, `space.16` horizontal
- Type: label / control (`foundations/typography.md`)
- Primary fill: `color.brand.500`; hover `color.brand.600`; label `color.neutral.0`
- Secondary: border `color.neutral.200`, fill `color.neutral.0`
- Destructive: fill or text `color.feedback.danger`

## States

Default, hover, pressed, focus, disabled, loading.

## Rules

- Disabled buttons need a visible reason nearby (helper text), not only a muted style.
- Loading replaces the label with a progress indicator and keeps the control width stable.
- Do not nest interactive elements inside a button.
