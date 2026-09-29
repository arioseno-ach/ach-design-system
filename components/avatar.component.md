---
id: avatar
name: Avatar
category: primitive
figma_component_name: "Avatar"
figma_url: "https://www.figma.com/design//?node-id=272-665"
status: draft
tokens_used:
  - avatar.initials.background
  - borderRadius.infinite
  - avatar.initials.text
---

# Avatar

> A visual representation of a user or entity, displayed as an image, initials, or fallback icon.
AKA: Profile Picture, User Icon, Profile Image, User Avatar, Thumbnail, Userpic

## Code contract

```typescript
interface AvatarProps {
  /** Visual variant: Type */
  Type?: 'Text' | 'Picture' | 'Logo OP' | 'Logo Covia' | 'Logo Credor' | 'Logo Achilles' | 'Slot';
  /** Visual variant: Size */
  Size?: 'Regular' | 'Small' | 'Tiny' | 'Extra Tiny';
  /** Visual variant: Roundness Type */
  Roundness Type?: 'Roundrect' | 'Round';
  children?: React.ReactNode;
  className?: string;
}
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Type | `Text`, `Picture`, `Logo OP`, `Logo Covia`, `Logo Credor`, `Logo Achilles`, `Slot` | `Text` | Visual variant: Type |
| Size | `Regular`, `Small`, `Tiny`, `Extra Tiny` | `Regular` | Visual variant: Size |
| Roundness Type | `Roundrect`, `Round` | `Round` | Visual variant: Roundness Type |

## Anatomy

```
1. [Root] Type=Text, Size=Regular, Roundness Type=Round (COMPONENT)
  2. [Label] CN (TEXT)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Type=Text, Size=Regular, Roundness Type=Round | fill | `#171717` | `avatar.initials.background` | `var(--ach-avatar-initials-background)` |
| Type=Text, Size=Regular, Roundness Type=Round | cornerRadius | `9999px` | `borderRadius.infinite` | `var(--ach-borderRadius-infinite)` |
| CN | fill | `#FFFFFF` | `avatar.initials.text` | `var(--ach-avatar-initials-text)` |
| CN | fontSize | `14px` | `—` | `—` |

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
