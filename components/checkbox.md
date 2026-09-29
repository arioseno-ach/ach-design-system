---
id: checkbox
name: Checkbox
category: primitive
figma_component_name: "Checkbox"
figma_url: "https://www.figma.com/design//?node-id=202-17759"
status: draft
tokens_used:
  - padding.2
  - checkbox.default.background
  - checkbox.default.border
  - borderRadius.xs
  - checkbox.default.text
---

# Checkbox

> A form control that allows users to select one or multiple options from a set.
AKA: Check Box, Tick Box, Check Mark, Selection Control, Multi-select Option

## Code contract

```typescript
interface CheckboxProps {
  /** Toggle: Show Label */
  Show Label?: boolean;
  /** Text content: Label */
  Label?: React.ReactNode;
  /** Visual variant: State */
  State?: 'Default' | 'Error' | 'Disabled';
  /** Visual variant: Checked? */
  Checked??: 'False' | 'True' | 'Indeterminate';
  children?: React.ReactNode;
  className?: string;
}
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| State | `Default`, `Error`, `Disabled` | `Default` | Visual variant: State |
| Checked? | `False`, `True`, `Indeterminate` | `False` | Visual variant: Checked? |

## Anatomy

```
1. [Root] State=Default, Checked?=False (COMPONENT)
  2. [Container] Checkbox (FRAME)
    3. [Element] Background (RECTANGLE)
  4. [Label] Label (TEXT)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| State=Default, Checked?=False | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Checkbox | itemSpacing | `10px` | `—` | `—` |
| Background | fill | `#FFFFFF` | `checkbox.default.background` | `var(--ach-checkbox-default-background)` |
| Background | stroke | `#BDBDBD` | `checkbox.default.border` | `var(--ach-checkbox-default-border)` |
| Background | cornerRadius | `4px` | `borderRadius.xs` | `var(--ach-borderRadius-xs)` |
| Label | fill | `#262626` | `checkbox.default.text` | `var(--ach-checkbox-default-text)` |
| Label | fontSize | `14px` | `—` | `—` |

## States

| State | Present | Notes |
| :--- | :--- | :--- |
| Default | ✅ | Defined in Figma |
| Hover | ❌ | Not found — add variant or document manually |
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
