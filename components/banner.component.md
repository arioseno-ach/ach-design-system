---
id: banner
name: Banner
category: feedback
figma_component_name: "Banner"
figma_url: "https://www.figma.com/design//?node-id=730-4990"
status: draft
tokens_used:
  - banner.default.background
  - banner.default.border
  - padding.6
  - padding.4
  - padding.3
  - banner.default.icon-wrapper-bg
  - borderRadius.sm
  - banner.default.icon
  - banner.default.text
  - button.outlined.primary.border
  - borderRadius.infinite
  - padding.2
  - button.outlined.primary.text
  - button.primary.background
  - button.primary.text
  - banner.default.close-icon
---

# Banner

> A prominent, full-width message bar displayed at the top of a page or section for important announcements.
AKA: Announcement Bar, Info Bar, Notification Banner, Top Banner, Flash Message

## Code contract

```typescript
interface BannerProps {
  /** Toggle: Show Buttons */
  Show Buttons?: boolean;
  /** Toggle: Show Close */
  Show Close?: boolean;
  /** Toggle: Show Icon */
  Show Icon?: boolean;
  /** Slot: Icon */
  Icon?: React.ReactNode;
  /** Text content: Label */
  Label?: React.ReactNode;
  /** Visual variant: Type */
  Type?: 'Default' | 'Success' | 'Warning' | 'Info' | 'Error';
  children?: React.ReactNode;
  className?: string;
}
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Type | `Default`, `Success`, `Warning`, `Info`, `Error` | `Default` | Visual variant: Type |

## Anatomy

```
1. [Root] Type=Default (COMPONENT)
  2. [Container] Main Content (FRAME)
    3. [Icon] Icon Wrapper (FRAME)
      4. [Icon] Icons/ui-actions/token (INSTANCE)
        5. [Element] Vector (VECTOR)
    6. [Label] Banner message text (TEXT)
  7. [Container] Group: Action (FRAME)
    8. [Container] Group: Buttons (SLOT)
      9. [Container] 02 Button Outlined v1.1 (INSTANCE)
        10. [Icon] Left icon (INSTANCE)
          11. [Element] Vector (VECTOR)
        12. [Label] Button (TEXT)
        13. [Icon] Right icon (INSTANCE)
          14. [Element] Vector (VECTOR)
      15. [Container] 01 Button Solid  v1.1 (INSTANCE)
        16. [Icon] Left icon (INSTANCE)
          17. [Element] Vector (VECTOR)
        18. [Label] Button (TEXT)
        19. [Icon] Right icon (INSTANCE)
          20. [Element] Vector (VECTOR)
    21. [Icon] Icons/ui-actions/close (INSTANCE)
      22. [Element] Vector (VECTOR)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Type=Default | fill | `#FAFAFA` | `banner.default.background` | `var(--ach-banner-default-background)` |
| Type=Default | stroke | `#DCDCDC` | `banner.default.border` | `var(--ach-banner-default-border)` |
| Type=Default | paddingTop | `24px` | `padding.6` | `var(--ach-padding-6)` |
| Type=Default | paddingRight | `24px` | `padding.6` | `var(--ach-padding-6)` |
| Type=Default | paddingBottom | `24px` | `padding.6` | `var(--ach-padding-6)` |
| Type=Default | paddingLeft | `24px` | `padding.6` | `var(--ach-padding-6)` |
| Type=Default | itemSpacing | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Main Content | itemSpacing | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Icon Wrapper | fill | `#EEEEEE` | `banner.default.icon-wrapper-bg` | `var(--ach-banner-default-icon-wrapper-bg)` |
| Icon Wrapper | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Icon Wrapper | itemSpacing | `10px` | `—` | `—` |
| Icons/ui-actions/token | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `banner.default.icon` | `var(--ach-banner-default-icon)` |
| Banner message text | fill | `#262626` | `banner.default.text` | `var(--ach-banner-default-text)` |
| Banner message text | fontSize | `16px` | `—` | `—` |
| Group: Action | itemSpacing | `24px` | `padding.6` | `var(--ach-padding-6)` |
| Group: Buttons | itemSpacing | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 02 Button Outlined v1.1 | stroke | `#DCDCDC` | `button.outlined.primary.border` | `var(--ach-button-outlined-primary-border)` |
| 02 Button Outlined v1.1 | cornerRadius | `9999px` | `borderRadius.infinite` | `var(--ach-borderRadius-infinite)` |
| 02 Button Outlined v1.1 | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 Button Outlined v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Button Outlined v1.1 | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 Button Outlined v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Button Outlined v1.1 | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Left icon | fill | `#262626` | `button.outlined.primary.text` | `var(--ach-button-outlined-primary-text)` |
| Vector | fill | `#262626` | `button.outlined.primary.text` | `var(--ach-button-outlined-primary-text)` |
| Button | fill | `#262626` | `button.outlined.primary.text` | `var(--ach-button-outlined-primary-text)` |
| Button | fontSize | `14px` | `—` | `—` |
| Right icon | fill | `#262626` | `button.outlined.primary.text` | `var(--ach-button-outlined-primary-text)` |
| Vector | fill | `#262626` | `button.outlined.primary.text` | `var(--ach-button-outlined-primary-text)` |
| 01 Button Solid  v1.1 | fill | `#171717` | `button.primary.background` | `var(--ach-button-primary-background)` |
| 01 Button Solid  v1.1 | cornerRadius | `9999px` | `borderRadius.infinite` | `var(--ach-borderRadius-infinite)` |
| 01 Button Solid  v1.1 | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 01 Button Solid  v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 01 Button Solid  v1.1 | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 01 Button Solid  v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 01 Button Solid  v1.1 | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Left icon | fill | `#FFFFFF` | `button.primary.text` | `var(--ach-button-primary-text)` |
| Vector | fill | `#FFFFFF` | `button.primary.text` | `var(--ach-button-primary-text)` |
| Button | fill | `#FFFFFF` | `button.primary.text` | `var(--ach-button-primary-text)` |
| Button | fontSize | `14px` | `—` | `—` |
| Right icon | fill | `#FFFFFF` | `button.primary.text` | `var(--ach-button-primary-text)` |
| Vector | fill | `#FFFFFF` | `button.primary.text` | `var(--ach-button-primary-text)` |
| Icons/ui-actions/close | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `banner.default.close-icon` | `var(--ach-banner-default-close-icon)` |

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
