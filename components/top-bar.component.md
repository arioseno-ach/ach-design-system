---
id: top-bar
name: TopBar
category: primitive
figma_component_name: "Top Bar"
figma_url: "https://www.figma.com/design//?node-id=1043-23681"
status: draft
tokens_used:
  - topbar.background
  - padding.6
  - padding.4
  - colors.neutral.1000
  - padding.2
  - padding.3
  - button.icon.inverse.bg
  - borderRadius.infinite
  - button.icon.inverse.icon
  - avatar.initials.background
  - avatar.initials.text
  - topbar.text
  - topbar.icon
  - divider.default
---

# TopBar

> The main horizontal navigation bar at the top of the application.
AKA: Header, App Bar, Navigation Bar, Navbar, Top Navigation, App Header, Toolbar

## Code contract

```typescript
interface TopBarProps {
  /** Toggle: Action Trail */
  Action Trail?: boolean;
  /** Toggle: Show Logo */
  Show Logo?: boolean;
  /** Toggle: Bordered */
  Bordered?: boolean;
  /** Visual variant: Breakpoint */
  Breakpoint?: 'Web' | 'Tab' | 'Mobile';
  /** Visual variant: isBordered */
  isBordered?: 'false';
  children?: React.ReactNode;
  className?: string;
}
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Breakpoint | `Web`, `Tab`, `Mobile` | `Web` | Visual variant: Breakpoint |
| isBordered | `false` | `false` | Visual variant: isBordered |

## Anatomy

```
1. [Root] Breakpoint=Web, isBordered=false (COMPONENT)
  2. [Icon] Topbar Icons and Account (FRAME)
    3. [Element] Header Logo (INSTANCE)
      4. [Element] ✅ Final - Black (FRAME)
        5. [Element] Vector (VECTOR)
        6. [Element] Vector (VECTOR)
        7. [Element] Vector (VECTOR)
        8. [Element] Vector (VECTOR)
        9. [Element] Vector (VECTOR)
        10. [Element] Vector (VECTOR)
        11. [Element] Vector (VECTOR)
        12. [Element] Vector (VECTOR)
        13. [Element] Vector (VECTOR)
    14. [Container] Spacer (FRAME)
    15. [Icon] Group: Icon Button (SLOT)
      16. [Icon] 04 Button Icon v1.1 (INSTANCE)
        17. [Icon] Icons (FRAME)
          18. [Icon] Icons/business-payments/shopping-cart (INSTANCE)
            19. [Element] Vector (VECTOR)
    20. [Container] Account (FRAME)
      21. [Avatar] 01 Avatar (INSTANCE)
        22. [Label] CN (TEXT)
      23. [Label] Account Name (TEXT)
      24. [Icon] Icons/hardware/keyboard-arrow-down (INSTANCE)
        25. [Element] Vector (VECTOR)
  26. [Divider] 01 Divider (INSTANCE)
    27. [Divider] Divider (RECTANGLE)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Breakpoint=Web, isBordered=false | fill | `#FFFFFF` | `topbar.background` | `var(--ach-topbar-background)` |
| Topbar Icons and Account | paddingRight | `24px` | `padding.6` | `var(--ach-padding-6)` |
| Topbar Icons and Account | paddingLeft | `24px` | `padding.6` | `var(--ach-padding-6)` |
| Topbar Icons and Account | itemSpacing | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Header Logo | fill | `#FFFFFF` | `—` | `—` |
| ✅ Final - Black | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#000000` | `colors.neutral.1000` | `var(--ach-colors-neutral-1000)` |
| Vector | fill | `#000000` | `colors.neutral.1000` | `var(--ach-colors-neutral-1000)` |
| Vector | fill | `#000000` | `colors.neutral.1000` | `var(--ach-colors-neutral-1000)` |
| Vector | fill | `#000000` | `colors.neutral.1000` | `var(--ach-colors-neutral-1000)` |
| Vector | fill | `#000000` | `colors.neutral.1000` | `var(--ach-colors-neutral-1000)` |
| Vector | fill | `#000000` | `colors.neutral.1000` | `var(--ach-colors-neutral-1000)` |
| Vector | fill | `#000000` | `colors.neutral.1000` | `var(--ach-colors-neutral-1000)` |
| Vector | fill | `#000000` | `colors.neutral.1000` | `var(--ach-colors-neutral-1000)` |
| Vector | fill | `#000000` | `colors.neutral.1000` | `var(--ach-colors-neutral-1000)` |
| Spacer | fill | `#FFFFFF` | `topbar.background` | `var(--ach-topbar-background)` |
| Spacer | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Spacer | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Spacer | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Spacer | paddingLeft | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Spacer | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Group: Icon Button | itemSpacing | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 04 Button Icon v1.1 | fill | `#FFFFFF` | `button.icon.inverse.bg` | `var(--ach-button-icon-inverse-bg)` |
| 04 Button Icon v1.1 | cornerRadius | `9999px` | `borderRadius.infinite` | `var(--ach-borderRadius-infinite)` |
| 04 Button Icon v1.1 | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 04 Button Icon v1.1 | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 04 Button Icon v1.1 | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 04 Button Icon v1.1 | paddingLeft | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 04 Button Icon v1.1 | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Icons | itemSpacing | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Icons/business-payments/shopping-cart | fill | `#262626` | `button.icon.inverse.icon` | `var(--ach-button-icon-inverse-icon)` |
| Vector | fill | `#262626` | `button.icon.inverse.icon` | `var(--ach-button-icon-inverse-icon)` |
| Account | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 01 Avatar | fill | `#171717` | `avatar.initials.background` | `var(--ach-avatar-initials-background)` |
| 01 Avatar | cornerRadius | `9999px` | `borderRadius.infinite` | `var(--ach-borderRadius-infinite)` |
| CN | fill | `#FFFFFF` | `avatar.initials.text` | `var(--ach-avatar-initials-text)` |
| CN | fontSize | `14px` | `—` | `—` |
| Account Name | fill | `#262626` | `topbar.text` | `var(--ach-topbar-text)` |
| Account Name | fontSize | `14px` | `—` | `—` |
| Icons/hardware/keyboard-arrow-down | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `topbar.icon` | `var(--ach-topbar-icon)` |
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
