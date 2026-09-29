---
id: sidebar-group-label
name: SidebarGroupLabel
category: layout
figma_component_name: "Sidebar Group Label"
figma_url: "https://www.figma.com/design//?node-id=269-1613"
status: draft
tokens_used:
  - padding.2
  - padding.3
  - sidebar.group-label.text
parent_components:
  - sidebar
---

# SidebarGroupLabel

> A label used to group related navigation items within a Sidebar.
AKA: Nav Section Label, Sidebar Section, Nav Group Header, Menu Group Label

## Relationships

**Parent components (this component is used inside):**
- [`Sidebar`](./sidebar.component.md)

## Code contract

```typescript
interface SidebarGroupLabelProps {
  /** Text content: Label */
  Label?: React.ReactNode;
  /** Visual variant: Size */
  Size?: 'S' | 'Medium' | 'Large';
  children?: React.ReactNode;
  className?: string;
}
```

## Usage

> This component is designed to be used inside [`Sidebar`](./sidebar.component.md).

```tsx
<Sidebar>
  <SidebarGroupLabel />
  <SidebarGroupLabel />
</Sidebar>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Size | `S`, `Medium`, `Large` | `S` | Visual variant: Size |

## Anatomy

```
1. [Root] Size=S (COMPONENT)
  2. [Label] GROUP LABEL (TEXT)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Size=S | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Size=S | paddingRight | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Size=S | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Size=S | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Size=S | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| GROUP LABEL | fill | `#737373` | `sidebar.group-label.text` | `var(--ach-sidebar-group-label-text)` |
| GROUP LABEL | fontSize | `10px` | `—` | `—` |

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


---

---
id: sidebar
name: Sidebar
category: layout
figma_component_name: "Sidebar"
figma_url: "https://www.figma.com/design//?node-id=1125-9352"
status: draft
tokens_used:
  - sidebar.background
  - sidebar.border
  - padding.4
  - padding.2
  - sidebar.profile.background
  - sidebar.profile.border
  - borderRadius.sm
  - padding.1
  - borderRadius.xs
  - padding.3
  - avatar.initials.background
  - borderRadius.infinite
  - avatar.initials.text
  - sidebar.profile.text
  - badge.soft.primary.background
  - 3xs
  - xs
  - 2xs
  - badge.solid.primary.icon
  - badge.soft.primary.icon
  - badge.soft.primary.text
  - sidebar.profile.text_secondary
  - sidebar.profile.icon
  - icon.ach-color-icon-default
  - sidebar.item.text
  - sidebar.group-label.text
  - avatar.logo.background
  - borderRadius.md
  - avatar.logo.icon
  - sidebar.item.secondary
child_components:
  - .sidebar-profile
  - sidebar-item
  - sidebar-group-label
---

# Sidebar

> A vertical navigation panel typically placed on the left side of a layout for app-level navigation.
AKA: Side Navigation, Sidenav, Nav Panel, Left Menu, Navigation Drawer, Side Menu

## Relationships

**Child components (used inside this component):**
- [`.Sidebar / Profile`](./.sidebar-profile.component.md)
- [`Sidebar Item`](./sidebar-item.component.md)
- [`Sidebar Group Label`](./sidebar-group-label.component.md)

## Code contract

```typescript
interface SidebarProps {
  /** Visual variant: isExpand */
  isExpand?: 'true' | 'false';
  children?: React.ReactNode; // Accepts: .Sidebar / Profile, Sidebar Item, Sidebar Group Label
  className?: string;
}
```

## Usage

```tsx
<Sidebar>
  <.SidebarProfile />
  <.SidebarProfile />
  <SidebarItem />
  <SidebarItem />
  <SidebarGroupLabel />
  <SidebarGroupLabel />
</Sidebar>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| isExpand | `true`, `false` | `true` | Visual variant: isExpand |

## Anatomy

```
1. [Root] isExpand=true (COMPONENT)
  2. [Container] Content (SLOT)
    3. [Container] .Sidebar / Profile (INSTANCE)
      4. [Container] Menu Item (FRAME)
        5. [Avatar] 01 Avatar (INSTANCE)
          6. [Label] CN (TEXT)
        7. [Container] AL (FRAME)
          8. [Label] Company Name (TEXT)
          9. [Badge] 01 Badge Solid (INSTANCE)
            10. [Icon] Left icon (INSTANCE)
              11. [Element] Vector (VECTOR)
            12. [Label] Label (TEXT)
            13. [Icon] Right icon (INSTANCE)
              14. [Element] Vector (VECTOR)
          15. [Label] NPWP Number (TEXT)
        16. [Icon] Icon (INSTANCE)
          17. [Element] Vector (VECTOR)
    18. [Container] Home (INSTANCE)
      19. [Icon] Icon (INSTANCE)
        20. [Element] Vector (VECTOR)
      21. [Label] Label (TEXT)
    22. [Container] Sidebar Group (FRAME)
      23. [Container] 03 Sidebar Group Label (INSTANCE)
        24. [Label] GROUP LABEL (TEXT)
      25. [Container] Document (INSTANCE)
        26. [Icon] Icon (INSTANCE)
          27. [Element] Vector (VECTOR)
        28. [Label] Label (TEXT)
      29. [Container] Sales Transaction (INSTANCE)
        30. [Icon] Icon (INSTANCE)
          31. [Element] Vector (VECTOR)
        32. [Label] Label (TEXT)
      33. [Container] Purchase Transaction (INSTANCE)
        34. [Icon] Icon (INSTANCE)
          35. [Element] Vector (VECTOR)
        36. [Label] Label (TEXT)
    37. [Container] Sidebar Group (FRAME)
      38. [Container] 03 Sidebar Group Label (INSTANCE)
        39. [Label] GROUP LABEL (TEXT)
      40. [Container] Tax & Compliance (FRAME)
        41. [Container] Tax & Compliance (INSTANCE)
          42. [Avatar] 01 Avatar (INSTANCE)
            43. [Element] Group 1000002861 (GROUP)
              44. [Element] Vector (VECTOR)
              45. [Element] Vector (VECTOR)
              46. [Element] Vector (VECTOR)
          47. [Container] Text Area (FRAME)
            48. [Label] Label (TEXT)
            49. [Label] Caption (TEXT)
      50. [Container] Cash & Financing (FRAME)
        51. [Container] Cash & Financing (INSTANCE)
          52. [Avatar] 01 Avatar (INSTANCE)
            53. [Element] Vector (VECTOR)
          54. [Container] Text Area (FRAME)
            55. [Label] Label (TEXT)
            56. [Label] Caption (TEXT)
      57. [Container] Insights & Commerce (FRAME)
        58. [Container] Insights & Commerce (INSTANCE)
          59. [Avatar] 01 Avatar (INSTANCE)
            60. [Element] Vector (VECTOR)
          61. [Container] Text Area (FRAME)
            62. [Label] Label (TEXT)
            63. [Label] Caption (TEXT)
    64. [Container] All Products (INSTANCE)
      65. [Icon] Icon (INSTANCE)
        66. [Element] Vector (VECTOR)
      67. [Label] Label (TEXT)
    68. [Element] Spacer (FRAME)
    69. [Container] Wrapper (FRAME)
      70. [Container] Settings (INSTANCE)
        71. [Icon] Icon (INSTANCE)
          72. [Element] Vector (VECTOR)
        73. [Label] Label (TEXT)
        74. [Icon] Status Icon (INSTANCE)
          75. [Element] Vector (VECTOR)
      76. [Container] Help & Support (INSTANCE)
        77. [Icon] Icon (INSTANCE)
          78. [Element] Vector (VECTOR)
        79. [Label] Label (TEXT)
        80. [Icon] Status Icon (INSTANCE)
          81. [Element] Vector (VECTOR)
      82. [Container] Collapse (INSTANCE)
        83. [Icon] Icon (INSTANCE)
          84. [Element] Vector (VECTOR)
        85. [Label] Label (TEXT)
        86. [Icon] Status Icon (INSTANCE)
          87. [Element] Vector (VECTOR)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| isExpand=true | fill | `#FFFFFF` | `sidebar.background` | `var(--ach-sidebar-background)` |
| isExpand=true | stroke | `#DCDCDC` | `sidebar.border` | `var(--ach-sidebar-border)` |
| isExpand=true | paddingTop | `16px` | `padding.4` | `var(--ach-padding-4)` |
| isExpand=true | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| isExpand=true | paddingBottom | `16px` | `padding.4` | `var(--ach-padding-4)` |
| isExpand=true | paddingLeft | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Content | itemSpacing | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .Sidebar / Profile | fill | `#FFFFFF` | `sidebar.profile.background` | `var(--ach-sidebar-profile-background)` |
| .Sidebar / Profile | stroke | `#DCDCDC` | `sidebar.profile.border` | `var(--ach-sidebar-profile-border)` |
| .Sidebar / Profile | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| .Sidebar / Profile | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| .Sidebar / Profile | paddingRight | `4px` | `padding.1` | `var(--ach-padding-1)` |
| .Sidebar / Profile | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| .Sidebar / Profile | paddingLeft | `4px` | `padding.1` | `var(--ach-padding-1)` |
| .Sidebar / Profile | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Menu Item | cornerRadius | `4px` | `borderRadius.xs` | `var(--ach-borderRadius-xs)` |
| Menu Item | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Menu Item | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Menu Item | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Menu Item | paddingLeft | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Menu Item | itemSpacing | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 01 Avatar | fill | `#171717` | `avatar.initials.background` | `var(--ach-avatar-initials-background)` |
| 01 Avatar | cornerRadius | `9999px` | `borderRadius.infinite` | `var(--ach-borderRadius-infinite)` |
| CN | fill | `#FFFFFF` | `avatar.initials.text` | `var(--ach-avatar-initials-text)` |
| CN | fontSize | `14px` | `—` | `—` |
| AL | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Company Name | fill | `#262626` | `sidebar.profile.text` | `var(--ach-sidebar-profile-text)` |
| Company Name | fontSize | `14px` | `—` | `—` |
| 01 Badge Solid | fill | `#E5E5E5` | `badge.soft.primary.background` | `var(--ach-badge-soft-primary-background)` |
| 01 Badge Solid | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 01 Badge Solid | paddingTop | `2px` | `3xs` | `var(--ach-3xs)` |
| 01 Badge Solid | paddingRight | `8px` | `xs` | `var(--ach-xs)` |
| 01 Badge Solid | paddingBottom | `2px` | `3xs` | `var(--ach-3xs)` |
| 01 Badge Solid | paddingLeft | `8px` | `xs` | `var(--ach-xs)` |
| 01 Badge Solid | itemSpacing | `4px` | `2xs` | `var(--ach-2xs)` |
| Left icon | fill | `#FFFFFF` | `badge.solid.primary.icon` | `var(--ach-badge-solid-primary-icon)` |
| Vector | fill | `#262626` | `badge.soft.primary.icon` | `var(--ach-badge-soft-primary-icon)` |
| Label | fill | `#262626` | `badge.soft.primary.text` | `var(--ach-badge-soft-primary-text)` |
| Label | fontSize | `12px` | `—` | `—` |
| Right icon | fill | `#FFFFFF` | `badge.solid.primary.icon` | `var(--ach-badge-solid-primary-icon)` |
| Vector | fill | `#262626` | `badge.soft.primary.icon` | `var(--ach-badge-soft-primary-icon)` |
| NPWP Number | fill | `#525252` | `sidebar.profile.text_secondary` | `var(--ach-sidebar-profile-text_secondary)` |
| NPWP Number | fontSize | `10px` | `—` | `—` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `sidebar.profile.icon` | `var(--ach-sidebar-profile-icon)` |
| Home | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Home | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Home | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Home | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Home | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Home | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `icon.ach-color-icon-default` | `var(--ach-icon-ach-color-icon-default)` |
| Label | fill | `#262626` | `sidebar.item.text` | `var(--ach-sidebar-item-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| 03 Sidebar Group Label | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 03 Sidebar Group Label | paddingRight | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 03 Sidebar Group Label | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 03 Sidebar Group Label | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 03 Sidebar Group Label | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| GROUP LABEL | fill | `#737373` | `sidebar.group-label.text` | `var(--ach-sidebar-group-label-text)` |
| GROUP LABEL | fontSize | `10px` | `—` | `—` |
| Document | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Document | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Document | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Document | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Document | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Document | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `icon.ach-color-icon-default` | `var(--ach-icon-ach-color-icon-default)` |
| Label | fill | `#262626` | `sidebar.item.text` | `var(--ach-sidebar-item-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Sales Transaction | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Sales Transaction | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Sales Transaction | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Sales Transaction | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Sales Transaction | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Sales Transaction | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `icon.ach-color-icon-default` | `var(--ach-icon-ach-color-icon-default)` |
| Label | fill | `#262626` | `sidebar.item.text` | `var(--ach-sidebar-item-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Purchase Transaction | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Purchase Transaction | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Purchase Transaction | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Purchase Transaction | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Purchase Transaction | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Purchase Transaction | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `icon.ach-color-icon-default` | `var(--ach-icon-ach-color-icon-default)` |
| Label | fill | `#262626` | `sidebar.item.text` | `var(--ach-sidebar-item-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| 03 Sidebar Group Label | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 03 Sidebar Group Label | paddingRight | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 03 Sidebar Group Label | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 03 Sidebar Group Label | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 03 Sidebar Group Label | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| GROUP LABEL | fill | `#737373` | `sidebar.group-label.text` | `var(--ach-sidebar-group-label-text)` |
| GROUP LABEL | fontSize | `10px` | `—` | `—` |
| Tax & Compliance | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Tax & Compliance | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Tax & Compliance | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Tax & Compliance | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Tax & Compliance | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Tax & Compliance | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 01 Avatar | fill | `#005CFF` | `avatar.logo.background` | `var(--ach-avatar-logo-background)` |
| 01 Avatar | cornerRadius | `12px` | `borderRadius.md` | `var(--ach-borderRadius-md)` |
| Vector | fill | `#FFFFFF` | `avatar.logo.icon` | `var(--ach-avatar-logo-icon)` |
| Vector | fill | `#FFFFFF` | `avatar.logo.icon` | `var(--ach-avatar-logo-icon)` |
| Vector | fill | `#FFFFFF` | `avatar.logo.icon` | `var(--ach-avatar-logo-icon)` |
| Label | fill | `#262626` | `sidebar.item.text` | `var(--ach-sidebar-item-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Caption | fill | `#525252` | `sidebar.item.secondary` | `var(--ach-sidebar-item-secondary)` |
| Caption | fontSize | `12px` | `—` | `—` |
| Cash & Financing | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Cash & Financing | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Cash & Financing | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Cash & Financing | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Cash & Financing | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Cash & Financing | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 01 Avatar | fill | `#005CFF` | `avatar.logo.background` | `var(--ach-avatar-logo-background)` |
| 01 Avatar | cornerRadius | `12px` | `borderRadius.md` | `var(--ach-borderRadius-md)` |
| Vector | fill | `#FFFFFF` | `avatar.logo.icon` | `var(--ach-avatar-logo-icon)` |
| Label | fill | `#262626` | `sidebar.item.text` | `var(--ach-sidebar-item-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Caption | fill | `#525252` | `sidebar.item.secondary` | `var(--ach-sidebar-item-secondary)` |
| Caption | fontSize | `12px` | `—` | `—` |
| Insights & Commerce | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Insights & Commerce | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Insights & Commerce | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Insights & Commerce | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Insights & Commerce | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Insights & Commerce | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 01 Avatar | fill | `#005CFF` | `avatar.logo.background` | `var(--ach-avatar-logo-background)` |
| 01 Avatar | cornerRadius | `12px` | `borderRadius.md` | `var(--ach-borderRadius-md)` |
| Vector | fill | `#FFFFFF` | `avatar.logo.icon` | `var(--ach-avatar-logo-icon)` |
| Label | fill | `#262626` | `sidebar.item.text` | `var(--ach-sidebar-item-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Caption | fill | `#525252` | `sidebar.item.secondary` | `var(--ach-sidebar-item-secondary)` |
| Caption | fontSize | `12px` | `—` | `—` |
| All Products | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| All Products | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| All Products | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| All Products | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| All Products | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| All Products | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `icon.ach-color-icon-default` | `var(--ach-icon-ach-color-icon-default)` |
| Label | fill | `#262626` | `sidebar.item.text` | `var(--ach-sidebar-item-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Settings | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Settings | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Settings | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Settings | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Settings | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Settings | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `icon.ach-color-icon-default` | `var(--ach-icon-ach-color-icon-default)` |
| Label | fill | `#262626` | `sidebar.item.text` | `var(--ach-sidebar-item-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Status Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `icon.ach-color-icon-default` | `var(--ach-icon-ach-color-icon-default)` |
| Help & Support | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Help & Support | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Help & Support | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Help & Support | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Help & Support | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Help & Support | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `icon.ach-color-icon-default` | `var(--ach-icon-ach-color-icon-default)` |
| Label | fill | `#262626` | `sidebar.item.text` | `var(--ach-sidebar-item-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Status Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `icon.ach-color-icon-default` | `var(--ach-icon-ach-color-icon-default)` |
| Collapse | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Collapse | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Collapse | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Collapse | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Collapse | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Collapse | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `icon.ach-color-icon-default` | `var(--ach-icon-ach-color-icon-default)` |
| Label | fill | `#262626` | `sidebar.item.text` | `var(--ach-sidebar-item-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Status Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `icon.ach-color-icon-default` | `var(--ach-icon-ach-color-icon-default)` |

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


---

---
id: .sidebar-profile
name: .SidebarProfile
category: layout
figma_component_name: ".Sidebar / Profile"
figma_url: "https://www.figma.com/design//?node-id=1354-23246"
status: draft
tokens_used:
  - sidebar.profile.background
  - sidebar.profile.border
  - borderRadius.sm
  - padding.1
  - padding.2
  - borderRadius.xs
  - padding.3
  - avatar.initials.background
  - borderRadius.infinite
  - avatar.initials.text
  - sidebar.profile.text
  - badge.soft.primary.background
  - 3xs
  - xs
  - 2xs
  - badge.solid.primary.icon
  - badge.soft.primary.icon
  - badge.soft.primary.text
  - sidebar.profile.text_secondary
  - sidebar.profile.icon
parent_components:
  - sidebar
---

# .SidebarProfile

## Relationships

**Parent components (this component is used inside):**
- [`Sidebar`](./sidebar.component.md)

## Code contract

```typescript
interface .SidebarProfileProps {
  /** Visual variant: isExpanded */
  isExpanded?: 'false' | 'true';
  children?: React.ReactNode;
  className?: string;
}
```

## Usage

> This component is designed to be used inside [`Sidebar`](./sidebar.component.md).

```tsx
<Sidebar>
  <.SidebarProfile />
  <.SidebarProfile />
</Sidebar>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| isExpanded | `false`, `true` | `false` | Visual variant: isExpanded |

## Anatomy

```
1. [Root] isExpanded=false (COMPONENT)
  2. [Container] Menu Item (FRAME)
    3. [Avatar] 01 Avatar (INSTANCE)
      4. [Label] CN (TEXT)
    5. [Container] AL (FRAME)
      6. [Label] Company Name (TEXT)
      7. [Badge] 01 Badge Solid (INSTANCE)
        8. [Icon] Left icon (INSTANCE)
          9. [Element] Vector (VECTOR)
        10. [Label] Label (TEXT)
        11. [Icon] Right icon (INSTANCE)
          12. [Element] Vector (VECTOR)
      13. [Label] NPWP Number (TEXT)
    14. [Icon] Icon (INSTANCE)
      15. [Element] Vector (VECTOR)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| isExpanded=false | fill | `#FFFFFF` | `sidebar.profile.background` | `var(--ach-sidebar-profile-background)` |
| isExpanded=false | stroke | `#DCDCDC` | `sidebar.profile.border` | `var(--ach-sidebar-profile-border)` |
| isExpanded=false | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| isExpanded=false | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| isExpanded=false | paddingRight | `4px` | `padding.1` | `var(--ach-padding-1)` |
| isExpanded=false | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| isExpanded=false | paddingLeft | `4px` | `padding.1` | `var(--ach-padding-1)` |
| isExpanded=false | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Menu Item | cornerRadius | `4px` | `borderRadius.xs` | `var(--ach-borderRadius-xs)` |
| Menu Item | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Menu Item | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Menu Item | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Menu Item | paddingLeft | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Menu Item | itemSpacing | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 01 Avatar | fill | `#171717` | `avatar.initials.background` | `var(--ach-avatar-initials-background)` |
| 01 Avatar | cornerRadius | `9999px` | `borderRadius.infinite` | `var(--ach-borderRadius-infinite)` |
| CN | fill | `#FFFFFF` | `avatar.initials.text` | `var(--ach-avatar-initials-text)` |
| CN | fontSize | `14px` | `—` | `—` |
| AL | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Company Name | fill | `#262626` | `sidebar.profile.text` | `var(--ach-sidebar-profile-text)` |
| Company Name | fontSize | `14px` | `—` | `—` |
| 01 Badge Solid | fill | `#E5E5E5` | `badge.soft.primary.background` | `var(--ach-badge-soft-primary-background)` |
| 01 Badge Solid | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 01 Badge Solid | paddingTop | `2px` | `3xs` | `var(--ach-3xs)` |
| 01 Badge Solid | paddingRight | `8px` | `xs` | `var(--ach-xs)` |
| 01 Badge Solid | paddingBottom | `2px` | `3xs` | `var(--ach-3xs)` |
| 01 Badge Solid | paddingLeft | `8px` | `xs` | `var(--ach-xs)` |
| 01 Badge Solid | itemSpacing | `4px` | `2xs` | `var(--ach-2xs)` |
| Left icon | fill | `#FFFFFF` | `badge.solid.primary.icon` | `var(--ach-badge-solid-primary-icon)` |
| Vector | fill | `#262626` | `badge.soft.primary.icon` | `var(--ach-badge-soft-primary-icon)` |
| Label | fill | `#262626` | `badge.soft.primary.text` | `var(--ach-badge-soft-primary-text)` |
| Label | fontSize | `12px` | `—` | `—` |
| Right icon | fill | `#FFFFFF` | `badge.solid.primary.icon` | `var(--ach-badge-solid-primary-icon)` |
| Vector | fill | `#262626` | `badge.soft.primary.icon` | `var(--ach-badge-soft-primary-icon)` |
| NPWP Number | fill | `#525252` | `sidebar.profile.text_secondary` | `var(--ach-sidebar-profile-text_secondary)` |
| NPWP Number | fontSize | `10px` | `—` | `—` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `sidebar.profile.icon` | `var(--ach-sidebar-profile-icon)` |

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


---

---
id: sidebar-item
name: SidebarItem
category: layout
figma_component_name: "Sidebar Item"
figma_url: "https://www.figma.com/design//?node-id=1357-941"
status: draft
tokens_used:
  - borderRadius.sm
  - padding.2
  - padding.3
  - sidebar.item.icon
  - sidebar.item.text
parent_components:
  - sidebar
---

# SidebarItem

> An individual navigation link within a Sidebar, representing a single destination or action.
AKA: Nav Item, Menu Item, Sidebar Link, Navigation Link, Nav Link

## Relationships

**Parent components (this component is used inside):**
- [`Sidebar`](./sidebar.component.md)

## Code contract

```typescript
interface SidebarItemProps {
  /** Slot: Icon */
  Icon?: React.ReactNode;
  /** Text content: Label */
  Label?: React.ReactNode;
  /** Toggle: Show Icon */
  Show Icon?: boolean;
  /** Visual variant: State */
  State?: 'Default' | 'Hover' | 'Active';
  /** Visual variant: Type */
  Type?: 'Default' | 'Product' | 'Dropdown' | 'Badge' | 'Submenu';
  /** Visual variant: isExpanded */
  isExpanded?: 'true' | 'false';
  children?: React.ReactNode;
  className?: string;
}
```

## Usage

> This component is designed to be used inside [`Sidebar`](./sidebar.component.md).

```tsx
<Sidebar>
  <SidebarItem />
  <SidebarItem />
</Sidebar>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| State | `Default`, `Hover`, `Active` | `Default` | Visual variant: State |
| Type | `Default`, `Product`, `Dropdown`, `Badge`, `Submenu` | `Default` | Visual variant: Type |
| isExpanded | `true`, `false` | `true` | Visual variant: isExpanded |

## Anatomy

```
1. [Root] State=Default, Type=Default, isExpanded=true (COMPONENT)
  2. [Icon] Icon (INSTANCE)
    3. [Element] Vector (VECTOR)
  4. [Label] Label (TEXT)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| State=Default, Type=Default, isExpanded=true | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| State=Default, Type=Default, isExpanded=true | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| State=Default, Type=Default, isExpanded=true | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| State=Default, Type=Default, isExpanded=true | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| State=Default, Type=Default, isExpanded=true | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| State=Default, Type=Default, isExpanded=true | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Vector | fill | `#262626` | `sidebar.item.icon` | `var(--ach-sidebar-item-icon)` |
| Label | fill | `#262626` | `sidebar.item.text` | `var(--ach-sidebar-item-text)` |
| Label | fontSize | `14px` | `—` | `—` |

## States

| State | Present | Notes |
| :--- | :--- | :--- |
| Default | ✅ | Defined in Figma |
| Hover | ✅ | Defined in Figma |
| Pressed | ✅ | Defined in Figma |
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
