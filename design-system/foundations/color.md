# Color

How to apply color tokens. Values live in `tokens/tokens.json`.

## Roles

| Role | Token | Use |
| --- | --- | --- |
| Page background | `color.neutral.0` / `50` | Surfaces |
| Text primary | `color.neutral.900` | Body and titles |
| Text secondary | `color.neutral.600` | Helper text |
| Border | `color.neutral.200` | Dividers, input borders |
| Brand / primary action | `color.brand.500` | Primary buttons, key links |
| Brand hover | `color.brand.600` | Hover / pressed on primary |
| Success | `color.feedback.success` | Confirmation, completed steps |
| Warning | `color.feedback.warning` | Caution, incomplete |
| Danger | `color.feedback.danger` | Errors, destructive actions |

## Rules

- Do not use brand color for body text.
- Danger is only for errors and destructive actions.
- Contrast must meet `foundations/accessibility.md`.
- Do not introduce one-off hex values.
