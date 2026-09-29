---
id: .03-selection
name: .03Selection
category: primitive
figma_component_name: ".03 Selection"
figma_url: "https://www.figma.com/design//?node-id=1988-6680"
status: draft
tokens_used:
  - select.menu.background
  - select.menu.border
  - borderRadius.sm
  - padding.2
  - padding.3
  - select.menu.item.text
  - select.menu.item.background_hover
  - select.menu.item.background_selected
  - select.menu.item.icon_selected
  - select.menu.item.text_disabled
child_components:
  - .03-selection-item
---

# .03Selection

> Option selection panel for Select. Nested in the Focus state and controlled by Show Selection.

## Relationships

**Child components (used inside this component):**
- [`.03 Selection Item`](./.03-selection-item.component.md)

## Code contract

```typescript
interface .03SelectionProps {
  children?: React.ReactNode; // Accepts: .03 Selection Item
  className?: string;
}
```

## Usage

```tsx
<.03Selection>
  <.03SelectionItem />
  <.03SelectionItem />
</.03Selection>
```

## Anatomy

```
1. [Root] .03 Selection (COMPONENT)
  2. [Container] Slot Selection (SLOT)
    3. [Container] Selection Item (INSTANCE)
      4. [Label] Option label (TEXT)
    5. [Container] Selection Item (INSTANCE)
      6. [Label] Option label (TEXT)
    7. [Container] Selection Item (INSTANCE)
      8. [Label] Option label (TEXT)
      9. [Icon] Check icon (INSTANCE)
        10. [Element] Vector (VECTOR)
    11. [Container] Selection Item (INSTANCE)
      12. [Label] Option label (TEXT)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| .03 Selection | fill | `#FFFFFF` | `select.menu.background` | `var(--ach-select-menu-background)` |
| .03 Selection | stroke | `#EEEEEE` | `select.menu.border` | `var(--ach-select-menu-border)` |
| .03 Selection | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| .03 Selection | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| .03 Selection | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| .03 Selection | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| .03 Selection | paddingLeft | `8px` | `padding.2` | `var(--ach-padding-2)` |
| .03 Selection | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Slot Selection | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Selection Item | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Selection Item | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Selection Item | paddingRight | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Selection Item | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Selection Item | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Selection Item | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Option label | fill | `#262626` | `select.menu.item.text` | `var(--ach-select-menu-item-text)` |
| Option label | fontSize | `14px` | `—` | `—` |
| Selection Item | fill | `#EEEEEE` | `select.menu.item.background_hover` | `var(--ach-select-menu-item-background_hover)` |
| Selection Item | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Selection Item | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Selection Item | paddingRight | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Selection Item | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Selection Item | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Selection Item | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Option label | fill | `#262626` | `select.menu.item.text` | `var(--ach-select-menu-item-text)` |
| Option label | fontSize | `14px` | `—` | `—` |
| Selection Item | fill | `#F5F5F5` | `select.menu.item.background_selected` | `var(--ach-select-menu-item-background_selected)` |
| Selection Item | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Selection Item | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Selection Item | paddingRight | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Selection Item | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Selection Item | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Selection Item | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Option label | fill | `#262626` | `select.menu.item.text` | `var(--ach-select-menu-item-text)` |
| Option label | fontSize | `14px` | `—` | `—` |
| Check icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#005CFF` | `select.menu.item.icon_selected` | `var(--ach-select-menu-item-icon_selected)` |
| Selection Item | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Selection Item | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Selection Item | paddingRight | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Selection Item | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Selection Item | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Selection Item | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Option label | fill | `#BDBDBD` | `select.menu.item.text_disabled` | `var(--ach-select-menu-item-text_disabled)` |
| Option label | fontSize | `14px` | `—` | `—` |

## States

| State | Present | Notes |
| :--- | :--- | :--- |
| Default | ✅ | Defined in Figma |
| Hover | ❌ | Not found — add variant or document manually |
| Pressed | ❌ | Not found — add variant or document manually |
| Focus | ❌ | Not found — add variant or document manually |
| Disabled | ❌ | Not found — add variant or document manually |
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
