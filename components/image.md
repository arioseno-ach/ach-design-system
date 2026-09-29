---
id: image
name: Image
category: primitive
figma_component_name: "Image"
figma_url: "https://www.figma.com/design//?node-id=1808-88"
status: draft
tokens_used:
  - image.placeholder.background
  - image.placeholder.border
  - borderRadius.sm
  - image.placeholder.icon
---

# Image

> A responsive image placeholder component with predefined aspect ratios. Swap the placeholder rectangle fill with your image. Available ratios: 1:1, 2:3, 3:2, 3:4, 4:3, 16:9.

## Code contract

```typescript
interface ImageProps {
  /** Visual variant: Ratio */
  Ratio?: '1:1' | '4:3' | '3:2' | '16:9' | '2:3' | '3:4';
  children?: React.ReactNode;
  className?: string;
}
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Ratio | `1:1`, `4:3`, `3:2`, `16:9`, `2:3`, `3:4` | `3:4` | Visual variant: Ratio |

## Anatomy

```
1. [Root] Ratio=3:4 (COMPONENT)
  2. [Image] [Change the image here] (RECTANGLE)
  3. [Icon] Icon (FRAME)
    4. [Element] Sun (ELLIPSE)
    5. [Element] Mountain1 (POLYGON)
    6. [Element] Mountain2 (POLYGON)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Ratio=3:4 | fill | `#FAFAFA` | `image.placeholder.background` | `var(--ach-image-placeholder-background)` |
| Ratio=3:4 | stroke | `#EEEEEE` | `image.placeholder.border` | `var(--ach-image-placeholder-border)` |
| Ratio=3:4 | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| [Change the image here] | fill | `#FAFAFA` | `image.placeholder.background` | `var(--ach-image-placeholder-background)` |
| Sun | fill | `#A3A3A3` | `image.placeholder.icon` | `var(--ach-image-placeholder-icon)` |
| Mountain1 | fill | `#A3A3A3` | `image.placeholder.icon` | `var(--ach-image-placeholder-icon)` |
| Mountain2 | fill | `#A3A3A3` | `image.placeholder.icon` | `var(--ach-image-placeholder-icon)` |

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
