---
id: datepicker
name: Datepicker
category: primitive
figma_component_name: "Datepicker"
figma_url: "https://www.figma.com/design//?node-id=1586-40174"
status: draft
tokens_used:
  - padding.1
  - input.labelText
  - input.background
  - input.border
  - borderRadius.sm
  - padding.2
  - padding.3
  - input.placeholder
  - datepicker.field.icon
  - input.helperText
---

# Datepicker

> A date selection input field that opens a calendar picker for choosing dates.
AKA: Date Picker, Calendar Input, Date Field, Date Selector, Calendar Picker

## Code contract

```typescript
interface DatepickerProps {
  /** Text content: Label */
  Label?: React.ReactNode;
  /** Text content: Placeholder */
  Placeholder?: React.ReactNode;
  /** Text content: Helper Text */
  Helper Text?: React.ReactNode;
  /** Toggle: Show Helper */
  Show Helper?: boolean;
  /** Toggle: Show Calendar */
  Show Calendar?: boolean;
  /** Text content: Value */
  Value?: React.ReactNode;
  /** Visual variant: State */
  State?: 'Default' | 'Value' | 'Focus' | 'Error' | 'Disabled';
  children?: React.ReactNode;
  className?: string;
}
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| State | `Default`, `Value`, `Focus`, `Error`, `Disabled` | `Default` | Visual variant: State |

## Anatomy

```
1. [Root] State=Default (COMPONENT)
  2. [Container] Label row (FRAME)
    3. [Label] Label (TEXT)
  4. [Container] Input (FRAME)
    5. [Label] Value (TEXT)
    6. [Icon] Calendar Icon (INSTANCE)
      7. [Element] Vector (VECTOR)
  8. [Label] Helper Text (TEXT)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| State=Default | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Label row | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Label | fill | `#737373` | `input.labelText` | `var(--ach-input-labelText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Input | fill | `#FFFFFF` | `input.background` | `var(--ach-input-background)` |
| Input | stroke | `#DCDCDC` | `input.border` | `var(--ach-input-border)` |
| Input | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Input | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Input | paddingRight | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Input | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Input | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Value | fill | `#A3A3A3` | `input.placeholder` | `var(--ach-input-placeholder)` |
| Value | fontSize | `14px` | `—` | `—` |
| Vector | fill | `#525252` | `datepicker.field.icon` | `var(--ach-datepicker-field-icon)` |
| Helper Text | fill | `#525252` | `input.helperText` | `var(--ach-input-helperText)` |
| Helper Text | fontSize | `14px` | `—` | `—` |

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
