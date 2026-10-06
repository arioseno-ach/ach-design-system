# Patterns and templates registry

Patterns are recurring layouts that compose components. Templates are full flows that compose patterns and components without redefining them.

## Patterns

| Pattern | Spec | Status |
| --- | --- | --- |
| Top bar | [top-bar.md](./top-bar.md) | draft |
| Bottom action bar | [bottom-action-bar.md](./bottom-action-bar.md) | draft |
| Dialog | [dialog.md](./dialog.md) | draft |

## Templates

| Template | Spec | Status |
| --- | --- | --- |
| Wizard | [wizard.md](./wizard.md) | draft |
| Onboarding flow | [onboarding-flow.md](./onboarding-flow.md) | draft |

## Adding an entry

1. Create `{name}.md` with frontmatter `kind: pattern` or `kind: template`.
2. Link components and patterns instead of copying their specs.
3. Add a row to the relevant table above.
