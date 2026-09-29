---
id: divider
name: Divider
category: primitive
figma_component_name: "Divider"
figma_url: "https://www.figma.com/design//?node-id=1107-2613"
status: draft
tokens_used:
  - divider.default
---

# Divider

> Also known as: Divider, Horizonal rule, Vertical rule
A separator between two elements, usually consisting of a horizontal line.

## Code contract

```typescript
interface DividerProps {
  /** Visual variant: Direction */
  Direction?: 'Vertical' | 'Horizontal';
  /** Visual variant: Size */
  Size?: 'S' | 'M' | 'L';
  /** Visual variant: Color */
  Color?: 'Default' | 'Subtle' | 'Disabled' | 'Inverse' | 'Strong';
  /** Visual variant: Spacing */
  Spacing?: 'True' | 'False';
  children?: React.ReactNode;
  className?: string;
}
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Direction | `Vertical`, `Horizontal` | `Horizontal` | Visual variant: Direction |
| Size | `S`, `M`, `L` | `S` | Visual variant: Size |
| Color | `Default`, `Subtle`, `Disabled`, `Inverse`, `Strong` | `Default` | Visual variant: Color |
| Spacing | `True`, `False` | `False` | Visual variant: Spacing |

## Anatomy

```
1. [Root] Direction=Horizontal, Size=S, Color=Default, Spacing=False (COMPONENT)
  2. [Divider] Divider (RECTANGLE)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |

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
