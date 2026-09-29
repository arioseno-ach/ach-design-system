---
id: .03-selection-item
name: .03SelectionItem
category: primitive
figma_component_name: ".03 Selection Item"
figma_url: "https://www.figma.com/design//?node-id=1999-101"
status: draft
tokens_used:
  - borderRadius.sm
  - padding.2
  - padding.3
  - select.menu.item.text
parent_components:
  - .03-selection
---

# .03SelectionItem

> Reusable option row for Input Selection. State controls default, hover, selected, and disabled treatments.

## Relationships

**Parent components (this component is used inside):**
- [`.03 Selection`](./.03-selection.component.md)

## Code contract

```typescript
interface .03SelectionItemProps {
  /** Text content: Label */
  Label?: React.ReactNode;
  /** Visual variant: State */
  State?: 'Default' | 'Hover' | 'Selected' | 'Disabled';
  children?: React.ReactNode;
  className?: string;
}
```

## Usage

> This component is designed to be used inside [`.03 Selection`](./.03-selection.component.md).

```tsx
<.03Selection>
  <.03SelectionItem />
  <.03SelectionItem />
</.03Selection>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| State | `Default`, `Hover`, `Selected`, `Disabled` | `Default` | Visual variant: State |

## Anatomy

```
1. [Root] State=Default (COMPONENT)
  2. [Label] Option label (TEXT)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| State=Default | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| State=Default | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| State=Default | paddingRight | `12px` | `padding.3` | `var(--ach-padding-3)` |
| State=Default | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| State=Default | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| State=Default | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Option label | fill | `#262626` | `select.menu.item.text` | `var(--ach-select-menu-item-text)` |
| Option label | fontSize | `14px` | `—` | `—` |

## States

| State | Present | Notes |
| :--- | :--- | :--- |
| Default | ✅ | Defined in Figma |
| Hover | ✅ | Defined in Figma |
| Pressed | ❌ | Not found — add variant or document manually |
| Focus | ❌ | Not found — add variant or document manually |
| Disabled | ✅ | Defined in Figma |
| Loading | ❌ | Not found — add variant or document manually |

## Do's and Don'ts

### Do's
- Always use design tokens — never hardcode hex values, pixel sizes, or font names.
- Provide helper text when a control is disabled to explain why.
- Use a single primary action per view or card.
- Follow the token mapping table for all style properties.
- Respect the anatomy structure — maintain the layer hierarchy.

### Don'ts
- Don't override token values with hardcoded `#hex` or inline styles.
- Don't skip disabled, loading, or error states.
- Don't nest this component inside itself.
- Don't remove required accessibility attributes (`role`, `aria-label`, etc.).
- Don't ignore the variant contract — always pass valid variant values.
