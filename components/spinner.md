---
id: spinner
name: Spinner
category: feedback
figma_component_name: "Spinner"
figma_url: "https://www.figma.com/design//?node-id=1657-9851"
status: draft
tokens_used:
  - spinner.primary.track
  - spinner.primary.indicator
---

# Spinner

> An animated loading indicator showing that content or an action is being processed.
AKA: Loader, Loading Spinner, Activity Indicator, Loading Icon, Busy Indicator, Throbber

## Code contract

```typescript
interface SpinnerProps {
  /** Visual variant: Size */
  Size?: 'xs' | 'sm' | 'md' | 'lg';
  /** Visual variant: Color */
  Color?: 'primary' | 'neutral' | 'brand' | 'success' | 'warning' | 'error' | 'info' | 'inverse';
  children?: React.ReactNode;
  className?: string;
}
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Size | `xs`, `sm`, `md`, `lg` | `xs` | Visual variant: Size |
| Color | `primary`, `neutral`, `brand`, `success`, `warning`, `error`, `info`, `inverse` | `primary` | Visual variant: Color |

## Anatomy

```
1. [Root] Size=xs, Color=primary (COMPONENT)
  2. [Element] Spinner (FRAME)
    3. [Element] Track (ELLIPSE)
    4. [Element] Indicator (VECTOR)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Size=xs, Color=primary | paddingTop | `2px` | `—` | `—` |
| Size=xs, Color=primary | paddingRight | `2px` | `—` | `—` |
| Size=xs, Color=primary | paddingBottom | `2px` | `—` | `—` |
| Size=xs, Color=primary | paddingLeft | `2px` | `—` | `—` |
| Track | stroke | `#EEEEEE` | `spinner.primary.track` | `var(--ach-spinner-primary-track)` |
| Indicator | stroke | `#262626` | `spinner.primary.indicator` | `var(--ach-spinner-primary-indicator)` |

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
