---
id: card
name: Card
category: layout
figma_component_name: "Card"
figma_url: "https://www.figma.com/design//?node-id=1045-24963"
status: draft
tokens_used:
  - card.background
  - card.border
  - card.borderRadius
  - card.padding
---

# Card

> A contained surface that groups related content and actions, typically with a border or elevation.
AKA: Tile, Content Card, Panel, Container, Surface, Content Block

## Code contract

```typescript
interface CardProps {
  /** Visual variant: isBordered */
  isBordered?: 'true' | 'false';
  /** Visual variant: isShadow */
  isShadow?: 'false' | 'true';
  /** Visual variant: withPadding */
  withPadding?: 'true' | 'false';
  /** Visual variant: slotDirection */
  slotDirection?: 'vertical' | 'horizontal';
  children?: React.ReactNode;
  className?: string;
}
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| isBordered | `true`, `false` | `true` | Visual variant: isBordered |
| isShadow | `false`, `true` | `false` | Visual variant: isShadow |
| withPadding | `true`, `false` | `true` | Visual variant: withPadding |
| slotDirection | `vertical`, `horizontal` | `vertical` | Visual variant: slotDirection |

## Anatomy

```
1. [Root] isBordered=true, isShadow=false, withPadding=true, slotDirection=vertical (COMPONENT)
  2. [Container] Slot Content (SLOT)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| isBordered=true, isShadow=false, withPadding=true, slotDirection=vertical | fill | `#FFFFFF` | `card.background` | `var(--ach-card-background)` |
| isBordered=true, isShadow=false, withPadding=true, slotDirection=vertical | stroke | `#DCDCDC` | `card.border` | `var(--ach-card-border)` |
| isBordered=true, isShadow=false, withPadding=true, slotDirection=vertical | cornerRadius | `8px` | `card.borderRadius` | `var(--ach-card-borderRadius)` |
| isBordered=true, isShadow=false, withPadding=true, slotDirection=vertical | paddingTop | `16px` | `card.padding` | `var(--ach-card-padding)` |
| isBordered=true, isShadow=false, withPadding=true, slotDirection=vertical | paddingRight | `16px` | `card.padding` | `var(--ach-card-padding)` |
| isBordered=true, isShadow=false, withPadding=true, slotDirection=vertical | paddingBottom | `16px` | `card.padding` | `var(--ach-card-padding)` |
| isBordered=true, isShadow=false, withPadding=true, slotDirection=vertical | paddingLeft | `16px` | `card.padding` | `var(--ach-card-padding)` |

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
