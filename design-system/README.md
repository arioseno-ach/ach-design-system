# Design system (agent entry point)

This folder is the source of truth for product UI, language, and interaction rules.

## How to use this repo

1. Read `design.md` for global rules, brand voice, and principles.
2. Check `business-context/` so copy and flows match the product, personas, and unit constraints.
3. Use `tokens/` as the only source of visual values. Do not invent hex, type sizes, or spacing.
4. Prefer existing `components/` and `patterns/` over new one-offs.
5. Compose screens from `templates/` when a flow already exists.
6. If you discover a mistake or missing rule, append it to `changelog/corrections-log.md` and fold the correction back into the relevant rule file.

## Layering

| Layer | Purpose | Do not |
| --- | --- | --- |
| Tokens | Raw values | Hardcode values in components |
| Foundations | How tokens are used | Redefine token values |
| Components | Single UI primitives | Encode full page flows |
| Patterns | Recurring layouts of components | Duplicate component specs |
| Templates | Full flows | Redefine components or patterns |

## File map

- `design.md` — global rules
- `tokens/` — `tokens.json` (source) and `tokens.css` (generated)
- `foundations/` — color, typography, spacing, accessibility
- `components/` — registry + per-component specs
- `patterns/` — registry + per-pattern specs
- `templates/` — registry + flow templates
- `business-context/` — product, voice, compliance
- `changelog/corrections-log.md` — rolling corrections
