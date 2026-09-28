# Typography

How to apply type tokens. Values live in `tokens/tokens.json`.

## Scale

| Role | Size | Weight | Line height |
| --- | --- | --- | --- |
| Page title | `font.size.xl` | semibold | tight |
| Section title | `font.size.lg` | semibold | tight |
| Body | `font.size.md` | regular | normal |
| Label / control | `font.size.md` | medium | normal |
| Helper / caption | `font.size.sm` | regular | normal |

## Rules

- One font family: `font.family.sans`.
- Do not mix more than two weights on a single screen unless a component spec requires it.
- Truncate long titles with an accessible full-text alternative (tooltip or expand).
- Buttons and inputs use the label / control style unless the component spec says otherwise.
