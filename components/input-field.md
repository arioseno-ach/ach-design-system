---
id: input-field
name: InputField
category: primitive
figma_component_name: "Input Field"
figma_url: "https://www.figma.com/design//?node-id=1715-287"
status: draft
tokens_used:
  - padding.1
  - input.labelText
  - input.errorText
  - input.background
  - input.border
  - borderRadius.sm
  - padding.2
  - padding.3
  - icon.ach-color-icon-subtle
  - input.placeholder
  - input.helperText
---

# InputField

> A single-line text input field for forms, with label, helper text, and validation states.
AKA: Text Field, Text Input, Form Input, Input Box, Form Field, Text Box

## Code contract

```typescript
interface InputFieldProps {
  /** Text content: Label */
  Label?: React.ReactNode;
  /** Text content: Placeholder */
  Placeholder?: React.ReactNode;
  /** Text content: Helper text */
  Helper text?: React.ReactNode;
  /** Toggle: Show label */
  Show label?: boolean;
  /** Toggle: Show helper text */
  Show helper text?: boolean;
  /** Slot: Left Icon Instance */
  Left Icon Instance?: React.ReactNode;
  /** Slot: Right Icon Instance */
  Right Icon Instance?: React.ReactNode;
  /** Toggle: Show left icon */
  Show left icon?: boolean;
  /** Toggle: Show right icon */
  Show right icon?: boolean;
  /** Toggle: Required */
  Required?: boolean;
  /** Visual variant: State */
  State?: 'Placeholder' | 'Value' | 'Focus' | 'Error' | 'Disabled';
  children?: React.ReactNode;
  className?: string;
}
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| State | `Placeholder`, `Value`, `Focus`, `Error`, `Disabled` | `Placeholder` | Visual variant: State |

## Anatomy

```
1. [Root] State=Placeholder (COMPONENT)
  2. [Container] Label row (FRAME)
    3. [Label] Label (TEXT)
    4. [Label] Required (TEXT)
  5. [Container] Input (FRAME)
    6. [Icon] Left icon (INSTANCE)
      7. [Element] Vector (VECTOR)
    8. [Label] Value (TEXT)
    9. [Icon] Right icon (INSTANCE)
      10. [Element] Vector (VECTOR)
  11. [Label] Helper text (TEXT)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| State=Placeholder | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Label row | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Label | fill | `#737373` | `input.labelText` | `var(--ach-input-labelText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Required | fill | `#A00000` | `input.errorText` | `var(--ach-input-errorText)` |
| Required | fontSize | `14px` | `—` | `—` |
| Input | fill | `#FFFFFF` | `input.background` | `var(--ach-input-background)` |
| Input | stroke | `#DCDCDC` | `input.border` | `var(--ach-input-border)` |
| Input | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Input | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Input | paddingRight | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Input | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Input | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Input | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Vector | fill | `#737373` | `icon.ach-color-icon-subtle` | `var(--ach-icon-ach-color-icon-subtle)` |
| Value | fill | `#A3A3A3` | `input.placeholder` | `var(--ach-input-placeholder)` |
| Value | fontSize | `14px` | `—` | `—` |
| Vector | fill | `#737373` | `icon.ach-color-icon-subtle` | `var(--ach-icon-ach-color-icon-subtle)` |
| Helper text | fill | `#525252` | `input.helperText` | `var(--ach-input-helperText)` |
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
