---
id: search-input
name: SearchInput
category: primitive
figma_component_name: "Search Input"
figma_url: "https://www.figma.com/design//?node-id=1996-49199"
status: draft
tokens_used:
  - search-input.background
  - search-input.border
  - borderRadius.infinite
  - padding.2
  - padding.3
  - search-input.icon
  - search-input.placeholder
---

# SearchInput

> Single-size search input with optional prepend or append filter action.

## Code contract

```typescript
interface SearchInputProps {
  /** Text content: Search text */
  Search text?: React.ReactNode;
  /** Text content: Filter label */
  Filter label?: React.ReactNode;
  /** Slot: Filter icon */
  Filter icon?: React.ReactNode;
  /** Visual variant: State */
  State?: 'Placeholder' | 'Focus' | 'Filled' | 'Disabled' | 'Error';
  /** Visual variant: Filter */
  Filter?: 'Hidden' | 'Prepend' | 'Append';
  children?: React.ReactNode;
  className?: string;
}
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| State | `Placeholder`, `Focus`, `Filled`, `Disabled`, `Error` | `Placeholder` | Visual variant: State |
| Filter | `Hidden`, `Prepend`, `Append` | `Hidden` | Visual variant: Filter |

## Anatomy

```
1. [Root] State=Placeholder, Filter=Hidden (COMPONENT)
  2. [Container] Search field (FRAME)
    3. [Icon] Search icon (INSTANCE)
      4. [Element] Vector (VECTOR)
    5. [Label] Search text (TEXT)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| State=Placeholder, Filter=Hidden | fill | `#FFFFFF` | `search-input.background` | `var(--ach-search-input-background)` |
| State=Placeholder, Filter=Hidden | stroke | `#DCDCDC` | `search-input.border` | `var(--ach-search-input-border)` |
| State=Placeholder, Filter=Hidden | cornerRadius | `9999px` | `borderRadius.infinite` | `var(--ach-borderRadius-infinite)` |
| Search field | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Search field | paddingRight | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Search field | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Search field | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Search field | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Search icon | fill | `#525252` | `search-input.icon` | `var(--ach-search-input-icon)` |
| Vector | fill | `#525252` | `search-input.icon` | `var(--ach-search-input-icon)` |
| Search text | fill | `#A3A3A3` | `search-input.placeholder` | `var(--ach-search-input-placeholder)` |
| Search text | fontSize | `14px` | `—` | `—` |

## States

| State | Present | Notes |
| :--- | :--- | :--- |
| Default | ✅ | Defined in Figma |
| Hover | ❌ | Not found — add variant or document manually |
| Pressed | ❌ | Not found — add variant or document manually |
| Focus | ✅ | Defined in Figma |
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
