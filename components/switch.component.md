---
id: switch
name: Switch
category: primitive
figma_component_name: "Switch"
figma_url: "https://www.figma.com/design//?node-id=906-3564"
status: draft
tokens_used:
  - padding.2
  - switch.background.unchecked
  - borderRadius.md
  - switch.toggle.default
  - switch.label.label
  - switch.label.subtitle
---

# Switch

> A toggle control for switching between on and off states, typically for binary settings.
AKA: Toggle, Toggle Switch, On/Off Switch, Binary Toggle, Flip Switch

## Code contract

```typescript
interface SwitchProps {
  /** Toggle: Show Label */
  Show Label?: boolean;
  /** Toggle: Show Secondary */
  Show Secondary?: boolean;
  /** Text content: Label Text */
  Label Text?: React.ReactNode;
  /** Text content: Secondary Text */
  Secondary Text?: React.ReactNode;
  /** Visual variant: Checked? */
  Checked??: 'False' | 'True';
  /** Visual variant: State */
  State?: 'Default' | 'Focus' | 'Disabled';
  children?: React.ReactNode;
  className?: string;
}
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Checked? | `False`, `True` | `False` | Visual variant: Checked? |
| State | `Default`, `Focus`, `Disabled` | `Default` | Visual variant: State |

## Anatomy

```
1. [Root] Checked?=False, State=Default (COMPONENT)
  2. [Element] Switch (FRAME)
    3. [Element] Background (RECTANGLE)
    4. [Element] Toggle (ELLIPSE)
  5. [Container] Text (FRAME)
    6. [Label] Label (TEXT)
    7. [Label] Secondary text (TEXT)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Checked?=False, State=Default | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Background | fill | `#BDBDBD` | `switch.background.unchecked` | `var(--ach-switch-background-unchecked)` |
| Background | cornerRadius | `12px` | `borderRadius.md` | `var(--ach-borderRadius-md)` |
| Toggle | fill | `#FFFFFF` | `switch.toggle.default` | `var(--ach-switch-toggle-default)` |
| Label | fill | `#262626` | `switch.label.label` | `var(--ach-switch-label-label)` |
| Label | fontSize | `14px` | `—` | `—` |
| Secondary text | fill | `#525252` | `switch.label.subtitle` | `var(--ach-switch-label-subtitle)` |
| Secondary text | fontSize | `12px` | `—` | `—` |

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
