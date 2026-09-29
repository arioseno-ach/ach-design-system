---
id: tooltip
name: Tooltip
category: feedback
figma_component_name: "Tooltip"
figma_url: "https://www.figma.com/design//?node-id=520-599"
status: draft
tokens_used:
  - tooltip.default.background
  - borderRadius.sm
  - hacks to fit scale.6
  - padding.2
  - tooltip.default.text
  - tooltip.default.arrow
---

# Tooltip

> A small popup that appears on hover or focus, providing additional context or information.
AKA: Info Tip, Hint, Popover Tip, Help Text, Hover Tip, Title Tooltip

## Code contract

```typescript
interface TooltipProps {
  /** Text content: Tooltip text */
  Tooltip text?: React.ReactNode;
  /** Visual variant: Side */
  Side?: 'Top' | 'Bottom' | 'Left' | 'Right';
  /** Visual variant: Style */
  Style?: 'Default' | 'Inverse';
  children?: React.ReactNode;
  className?: string;
}
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Side | `Top`, `Bottom`, `Left`, `Right` | `Top` | Visual variant: Side |
| Style | `Default`, `Inverse` | `Default` | Visual variant: Style |

## Anatomy

```
1. [Root] Side=Top, Style=Default (COMPONENT)
  2. [Label] Tooltip text (TEXT)
  3. [Element] Arrow (VECTOR)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Side=Top, Style=Default | fill | `#262626` | `tooltip.default.background` | `var(--ach-tooltip-default-background)` |
| Side=Top, Style=Default | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Side=Top, Style=Default | paddingTop | `6px` | `hacks to fit scale.6` | `var(--ach-hacks to fit scale-6)` |
| Side=Top, Style=Default | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Side=Top, Style=Default | paddingBottom | `6px` | `hacks to fit scale.6` | `var(--ach-hacks to fit scale-6)` |
| Side=Top, Style=Default | paddingLeft | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Side=Top, Style=Default | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Tooltip text | fill | `#FFFFFF` | `tooltip.default.text` | `var(--ach-tooltip-default-text)` |
| Tooltip text | fontSize | `12px` | `—` | `—` |
| Arrow | fill | `#262626` | `tooltip.default.arrow` | `var(--ach-tooltip-default-arrow)` |

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
