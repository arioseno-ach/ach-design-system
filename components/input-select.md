---
id: input-select
name: InputSelect
category: primitive
figma_component_name: "Input Select"
figma_url: "https://www.figma.com/design//?node-id=1988-334"
status: draft
tokens_used:
  - padding.2
  - select.label.text
  - select.helper.text_error
  - select.field.background
  - select.field.border
  - borderRadius.sm
  - padding.3
  - select.field.icon
  - select.field.placeholder
  - select.helper.text
---

# InputSelect

> Form input for selecting one predefined option. Use Show menu to display or hide the contained option list.

## Code contract

```typescript
interface InputSelectProps {
  /** Toggle: Show Selection */
  Show Selection?: boolean;
  /** Text content: Label */
  Label?: React.ReactNode;
  /** Text content: Selected value */
  Selected value?: React.ReactNode;
  /** Text content: Helper text */
  Helper text?: React.ReactNode;
  /** Toggle: Show label */
  Show label?: boolean;
  /** Toggle: Show helper text */
  Show helper text?: boolean;
  /** Toggle: Required */
  Required?: boolean;
  /** Toggle: Show left icon */
  Show left icon?: boolean;
  /** Visual variant: State */
  State?: 'Placeholder' | 'Value' | 'Multiple Value' | 'Focus' | 'Error' | 'Disabled';
  children?: React.ReactNode;
  className?: string;
}
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| State | `Placeholder`, `Value`, `Multiple Value`, `Focus`, `Error`, `Disabled` | `Placeholder` | Visual variant: State |

## Anatomy

```
1. [Root] State=Placeholder (COMPONENT)
  2. [Container] Label row (FRAME)
    3. [Label] Label (TEXT)
    4. [Label] Required indicator (TEXT)
  5. [Container] Control (FRAME)
    6. [Icon] Left icon (ELLIPSE)
    7. [Label] Selected value (TEXT)
    8. [Element] chevron-down (FRAME)
      9. [Element] Vector (VECTOR)
  10. [Label] Helper text (TEXT)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| State=Placeholder | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Label row | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Label | fill | `#737373` | `select.label.text` | `var(--ach-select-label-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Required indicator | fill | `#A00000` | `select.helper.text_error` | `var(--ach-select-helper-text_error)` |
| Required indicator | fontSize | `14px` | `—` | `—` |
| Control | fill | `#FFFFFF` | `select.field.background` | `var(--ach-select-field-background)` |
| Control | stroke | `#DCDCDC` | `select.field.border` | `var(--ach-select-field-border)` |
| Control | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Control | paddingRight | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Control | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Control | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Left icon | stroke | `#262626` | `select.field.icon` | `var(--ach-select-field-icon)` |
| Selected value | fill | `#A3A3A3` | `select.field.placeholder` | `var(--ach-select-field-placeholder)` |
| Selected value | fontSize | `14px` | `—` | `—` |
| Vector | stroke | `#262626` | `select.field.icon` | `var(--ach-select-field-icon)` |
| Helper text | fill | `#525252` | `select.helper.text` | `var(--ach-select-helper-text)` |
| Helper text | fontSize | `14px` | `—` | `—` |

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
