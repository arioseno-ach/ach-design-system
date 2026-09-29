---
id: progress-bar
name: ProgressBar
category: feedback
figma_component_name: "Progress Bar"
figma_url: "https://www.figma.com/design//?node-id=1175-15733"
status: draft
tokens_used:
  - padding.2
  - progress-bar.track
  - progress-bar.label
---

# ProgressBar

> A horizontal bar indicator showing the completion progress of a task or process.
AKA: Progress Indicator, Loading Bar, Status Bar, Completion Bar, Linear Progress

## Code contract

```typescript
interface ProgressBarProps {
  /** Toggle: Show Label */
  Show Label?: boolean;
  /** Visual variant: Size */
  Size?: 'Small' | 'Medium' | 'Large';
  /** Visual variant: Percentage */
  Percentage?: '0%' | '25%' | '50%' | '75%' | '100%';
  children?: React.ReactNode;
  className?: string;
}
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Size | `Small`, `Medium`, `Large` | `Small` | Visual variant: Size |
| Percentage | `0%`, `25%`, `50%`, `75%`, `100%` | `0%` | Visual variant: Percentage |

## Anatomy

```
1. [Badge] Size=Small, Percentage=0% (COMPONENT)
  2. [Container] Track (FRAME)
  3. [Label] Label (TEXT)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Size=Small, Percentage=0% | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Track | fill | `#F5F5F5` | `progress-bar.track` | `var(--ach-progress-bar-track)` |
| Track | cornerRadius | `2px` | `—` | `—` |
| Label | fill | `#737373` | `progress-bar.label` | `var(--ach-progress-bar-label)` |
| Label | fontSize | `10px` | `—` | `—` |

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
