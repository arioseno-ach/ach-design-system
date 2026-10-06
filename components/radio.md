---
id: radio
name: Radio
category: primitive
figma_component_name: "Radio"
figma_url: "https://www.figma.com/design//?node-id=1286-64640"
status: draft
tokens_used:
  - padding.2
  - radio.background
  - radio.default.border
  - radio.default.text
---

# Radio

> A form control that allows users to select exactly one option from a set of mutually exclusive choices.
AKA: Radio Button, Radio Group, Option Button, Single Select, Radio Input

## Code contract

```typescript
interface RadioProps {
  /** Toggle: Show Label */
  Show Label?: boolean;
  /** Text content: Label */
  Label?: React.ReactNode;
  /** Visual variant: Checked? */
  Checked??: 'False' | 'True';
  /** Visual variant: State */
  State?: 'Default' | 'Error' | 'Disabled';
  children?: React.ReactNode;
  className?: string;
}
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Checked? | `False`, `True` | `False` | Visual variant: Checked? |
| State | `Default`, `Error`, `Disabled` | `Default` | Visual variant: State |

## Anatomy

```
1. [Root] Checked?=False, State=Default (COMPONENT)
  2. [Element] Radio (FRAME)
    3. [Element] Background (ELLIPSE)
  4. [Label] Label (TEXT)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Checked?=False, State=Default | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Background | fill | `#FFFFFF` | `radio.background` | `var(--ach-radio-background)` |
| Background | stroke | `#DCDCDC` | `radio.default.border` | `var(--ach-radio-default-border)` |
| Background | cornerRadius | `3px` | `—` | `—` |
| Label | fill | `#262626` | `radio.default.text` | `var(--ach-radio-default-text)` |
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
