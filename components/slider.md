---
id: slider
name: Slider
category: primitive
figma_component_name: "Slider"
figma_url: "https://www.figma.com/design//?node-id=2260-191"
status: draft
tokens_used:
  - slider.track.background
  - borderRadius.sm
  - slider.track.fill
  - slider.marker.background
  - borderRadius.infinite
  - slider.marker.border
---

# Slider

> A draggable input control for selecting a value within a defined range.
AKA: Range Slider, Range Input, Scrubber, Track Bar, Seek Bar, Volume Control

## Code contract

```typescript
interface SliderProps {
  /** Visual variant: Orientation */
  Orientation?: 'Horizontal' | 'Vertical';
  /** Visual variant: Type */
  Type?: 'Default' | 'Range narrow' | 'Range wide';
  children?: React.ReactNode;
  className?: string;
}
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Orientation | `Horizontal`, `Vertical` | `Horizontal` | Visual variant: Orientation |
| Type | `Default`, `Range narrow`, `Range wide` | `Default` | Visual variant: Type |

## Anatomy

```
1. [Root] Orientation=Horizontal, Type=Default (COMPONENT)
  2. [Element] Overall (RECTANGLE)
  3. [Element] Value (RECTANGLE)
  4. [Element] .Marker (INSTANCE)
    5. [Element] Fake Ellipse (RECTANGLE)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Overall | fill | `#EEEEEE` | `slider.track.background` | `var(--ach-slider-track-background)` |
| Overall | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Value | fill | `#262626` | `slider.track.fill` | `var(--ach-slider-track-fill)` |
| .Marker | fill | `#FFFFFF` | `slider.marker.background` | `var(--ach-slider-marker-background)` |
| .Marker | cornerRadius | `9999px` | `borderRadius.infinite` | `var(--ach-borderRadius-infinite)` |
| Fake Ellipse | fill | `#FFFFFF` | `slider.marker.background` | `var(--ach-slider-marker-background)` |
| Fake Ellipse | stroke | `#404040` | `slider.marker.border` | `var(--ach-slider-marker-border)` |
| Fake Ellipse | cornerRadius | `9999px` | `borderRadius.infinite` | `var(--ach-borderRadius-infinite)` |

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
