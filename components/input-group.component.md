---
id: input-group
name: InputGroup
category: primitive
figma_component_name: "Input Group"
figma_url: "https://www.figma.com/design//?node-id=2026-8421"
status: draft
tokens_used:
  - padding.2
  - input-group.label.text
  - input-group.error.text
  - input-group.default.background
  - input-group.default.border
  - borderRadius.sm
  - padding.3
  - input-group.default.text
  - input-group.default.placeholder
  - input-group.default.icon
---

# InputGroup

> A grouped input layout combining a label with an input field and optional addons (prepend/append).
AKA: Input Addon, Input with Prefix, Compound Input, Grouped Field

## Code contract

```typescript
interface InputGroupProps {
  /** Text content: Label */
  Label?: React.ReactNode;
  /** Toggle: Required */
  Required?: boolean;
  /** Toggle: Show label */
  Show label?: boolean;
  /** Text content: Supporting text */
  Supporting text?: React.ReactNode;
  /** Toggle: Show supporting text */
  Show supporting text?: boolean;
  /** Toggle: Show prepend */
  Show prepend?: boolean;
  /** Toggle: Show append */
  Show append?: boolean;
  /** Text content: Value */
  Value?: React.ReactNode;
  /** Toggle: Show field icon */
  Show field icon?: boolean;
  /** Slot: Field icon */
  Field icon?: React.ReactNode;
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
  5. [Container] Control (FRAME)
    6. [Container] Prepend content (SLOT)
      7. [Label] Default content (TEXT)
    8. [Divider] Leading divider (RECTANGLE)
    9. [Container] Field content (FRAME)
      10. [Label] Value (TEXT)
      11. [Icon] Info icon (INSTANCE)
        12. [Element] Vector (VECTOR)
    13. [Divider] Trailing divider (RECTANGLE)
    14. [Container] Append content (SLOT)
      15. [Label] Default content (TEXT)
  16. [Container] Supporting message (FRAME)
    17. [Icon] Information icon (INSTANCE)
      18. [Element] Vector (VECTOR)
    19. [Label] Message (TEXT)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| State=Placeholder | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Label row | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Label | fill | `#525252` | `input-group.label.text` | `var(--ach-input-group-label-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Required | fill | `#A00000` | `input-group.error.text` | `var(--ach-input-group-error-text)` |
| Required | fontSize | `14px` | `—` | `—` |
| Control | fill | `#FFFFFF` | `input-group.default.background` | `var(--ach-input-group-default-background)` |
| Control | stroke | `#DCDCDC` | `input-group.default.border` | `var(--ach-input-group-default-border)` |
| Control | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Prepend content | paddingRight | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Prepend content | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Default content | fill | `#262626` | `input-group.default.text` | `var(--ach-input-group-default-text)` |
| Default content | fontSize | `14px` | `—` | `—` |
| Leading divider | fill | `#DCDCDC` | `input-group.default.border` | `var(--ach-input-group-default-border)` |
| Field content | paddingRight | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Field content | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Field content | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Value | fill | `#A3A3A3` | `input-group.default.placeholder` | `var(--ach-input-group-default-placeholder)` |
| Value | fontSize | `14px` | `—` | `—` |
| Info icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `input-group.default.icon` | `var(--ach-input-group-default-icon)` |
| Trailing divider | fill | `#DCDCDC` | `input-group.default.border` | `var(--ach-input-group-default-border)` |
| Append content | paddingRight | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Append content | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Default content | fill | `#262626` | `input-group.default.text` | `var(--ach-input-group-default-text)` |
| Default content | fontSize | `14px` | `—` | `—` |
| Supporting message | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Information icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `input-group.default.text` | `var(--ach-input-group-default-text)` |
| Message | fill | `#262626` | `input-group.default.text` | `var(--ach-input-group-default-text)` |
| Message | fontSize | `14px` | `—` | `—` |

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
