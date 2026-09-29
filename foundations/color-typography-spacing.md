# Color, typography, and spacing

How to apply color, typography, and spacing tokens. Values live in [`tokens/tokens.json`](../tokens/tokens.json).

## Color roles

| Role | Token | Use |
| --- | --- | --- |
| Page background | `color.neutral.0` / `color.neutral.50` | Surfaces |
| Text primary | `color.neutral.900` | Body and titles |
| Text secondary | `color.neutral.600` | Helper text |
| Border | `color.neutral.200` | Dividers and input borders |
| Brand / primary action | `color.brand.500` | Primary buttons and key links |
| Brand hover | `color.brand.600` | Hover and pressed primary controls |
| Success | `color.feedback.success` | Confirmation and completed steps |
| Warning | `color.feedback.warning` | Caution and incomplete work |
| Danger | `color.feedback.danger` | Errors and destructive actions |

### Color rules

- Do not use brand color for body text.
- Danger is only for errors and destructive actions.
- Contrast must meet [`accessibility.md`](./accessibility.md).
- Do not introduce one-off color values.

## Typography scale

| Role | Size token | Weight | Line-height role |
| --- | --- | --- | --- |
| Page title | `font.size.xl` | semibold | tight |
| Section title | `font.size.lg` | semibold | tight |
| Body | `font.size.md` | regular | normal |
| Label / control | `font.size.md` | medium | normal |
| Helper / caption | `font.size.sm` | regular | normal |

### Typography rules

- Use one font family: `font.family.sans`.
- Do not mix more than two weights on a single screen unless a component spec requires it.
- Truncate long titles with an accessible full-text alternative, such as a tooltip or expand control.
- Buttons and inputs use the label / control style unless the component spec says otherwise.

## Spacing use

| Context | Token |
| --- | --- |
| Tight related items, such as icon + label | `space.4` / `space.8` |
| Form field stack | `space.12` / `space.16` |
| Section padding | `space.16` / `space.24` |
| Screen edge on mobile | `space.16` |
| Pattern gutters, such as top bar and bottom bar | `space.16` |

### Spacing rules

- Use only spacing-scale tokens.
- Nested spacing should step down, for example section `space.24`, then inner stack `space.16` or `space.12`.
- Touch targets follow the minimum in [`accessibility.md`](./accessibility.md).
