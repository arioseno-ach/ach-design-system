---
id: text-area
name: TextArea
category: primitive
figma_component_name: "Text Area"
figma_url: "https://www.figma.com/design//?node-id=1968-47735"
status: draft
tokens_used:
  - padding.2
  - textarea.label
  - textarea.error_text
  - input.background
  - input.border
  - borderRadius.sm
  - textarea.background
  - textarea.border
  - padding.3
  - textarea.placeholder
  - textarea.supporting_text
  - textarea.resizable
---

# TextArea

> Single-size multiline text area with five states and an in-field character counter.

## Code contract

```typescript
interface TextAreaProps {
  /** Text content: Label */
  Label?: React.ReactNode;
  /** Text content: Value */
  Value?: React.ReactNode;
  /** Text content: Helper text */
  Helper text?: React.ReactNode;
  /** Text content: Counter */
  Counter?: React.ReactNode;
  /** Toggle: Show label */
  Show label?: boolean;
  /** Toggle: Show helper text */
  Show helper text?: boolean;
  /** Toggle: Show counter */
  Show counter?: boolean;
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
  5. [Container] Field area (FRAME)
    6. [Container] Field (FRAME)
      7. [Label] Value (TEXT)
      8. [Container] Meta row (FRAME)
        9. [Label] Counter (TEXT)
        10. [Element] Resizable (VECTOR)
  11. [Label] Helper text (TEXT)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| State=Placeholder | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Label row | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Label | fill | `#737373` | `textarea.label` | `var(--ach-textarea-label)` |
| Label | fontSize | `14px` | `—` | `—` |
| Required | fill | `#A00000` | `textarea.error_text` | `var(--ach-textarea-error_text)` |
| Required | fontSize | `14px` | `—` | `—` |
| Field area | fill | `#FFFFFF` | `input.background` | `var(--ach-input-background)` |
| Field area | stroke | `#DCDCDC` | `input.border` | `var(--ach-input-border)` |
| Field area | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Field | fill | `#FFFFFF` | `textarea.background` | `var(--ach-textarea-background)` |
| Field | stroke | `#DCDCDC` | `textarea.border` | `var(--ach-textarea-border)` |
| Field | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Field | paddingTop | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Field | paddingRight | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Field | paddingBottom | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Field | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Field | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Value | fill | `#A3A3A3` | `textarea.placeholder` | `var(--ach-textarea-placeholder)` |
| Value | fontSize | `14px` | `—` | `—` |
| Meta row | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Counter | fill | `#525252` | `textarea.supporting_text` | `var(--ach-textarea-supporting_text)` |
| Counter | fontSize | `14px` | `—` | `—` |
| Resizable | stroke | `#DCDCDC` | `textarea.resizable` | `var(--ach-textarea-resizable)` |
| Helper text | fill | `#525252` | `textarea.supporting_text` | `var(--ach-textarea-supporting_text)` |
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
