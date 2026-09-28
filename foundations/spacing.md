# Spacing

How to apply space tokens. Values live in `tokens/tokens.json`.

## Scale

`0`, `4`, `8`, `12`, `16`, `24`, `32`, `48`.

## Common use

| Context | Token |
| --- | --- |
| Tight related items (icon + label) | `space.4` / `space.8` |
| Form field stack | `space.12` / `space.16` |
| Section padding | `space.16` / `space.24` |
| Screen edge (mobile) | `space.16` |
| Pattern gutters (top bar, bottom bar) | `space.16` |

## Rules

- Use only scale steps. No `10px`, `18px`, or arbitrary values.
- Nested spacing should step down (section `24`, inner stack `16` or `12`).
- Touch targets: see `foundations/accessibility.md` (minimum 44×44).
