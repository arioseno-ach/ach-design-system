---
id: drawer
name: Drawer
category: primitive
figma_component_name: "Drawer"
figma_url: "https://www.figma.com/design//?node-id=1103-1217"
status: draft
tokens_used:
  - drawer.background
  - drawer.border
  - padding.4
  - drawer.title-text
  - drawer.icon
  - padding.1
  - padding.2
  - button.outlined.neutral.border
  - borderRadius.infinite
  - button.outlined.neutral.text
  - button.primary.background
  - button.primary.text
child_components:
  - .drawer-header
  - .drawer-footer
---

# Drawer

> A panel that slides in from the edge of the screen, overlaying the main content.
AKA: Side Panel, Slide-over, Sheet, Side Sheet, Off-canvas, Flyout Panel

## Relationships

**Child components (used inside this component):**
- [`.Drawer Header`](./.drawer-header.component.md)
- [`.Drawer Footer`](./.drawer-footer.component.md)

## Code contract

```typescript
interface DrawerProps {
  /** Visual variant: Overlay */
  Overlay?: 'false' | 'true';
  children?: React.ReactNode; // Accepts: .Drawer Header, .Drawer Footer
  className?: string;
}
```

## Usage

```tsx
<Drawer>
  <.DrawerHeader />
  <.DrawerHeader />
  <.DrawerFooter />
  <.DrawerFooter />
</Drawer>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Overlay | `false`, `true` | `true` | Visual variant: Overlay |

## Anatomy

```
1. [Root] Overlay=true (COMPONENT)
  2. [Container] Overlay (FRAME)
    3. [Element] bg (RECTANGLE)
  4. [Container] Drawer Wrapper (FRAME)
    5. [Container] .Drawer Header (INSTANCE)
      6. [Container] Content (SLOT)
        7. [Container] Drawer Title (FRAME)
          8. [Label] Drawer Title (TEXT)
        9. [Icon] Icons/ui-actions/close (INSTANCE)
          10. [Element] Vector (VECTOR)
    11. [Container] Drawer Content (FRAME)
      12. [Container] Main Content (SLOT)
    13. [Container] .Drawer Footer (INSTANCE)
      14. [Container] Content (SLOT)
        15. [Container] Button Group (FRAME)
          16. [Container] 02 Button Outlined v1.1 (INSTANCE)
            17. [Icon] Left icon (INSTANCE)
              18. [Element] Vector (VECTOR)
            19. [Label] Button (TEXT)
            20. [Icon] Right icon (INSTANCE)
              21. [Element] Vector (VECTOR)
          22. [Container] 01 Button Solid  v1.1 (INSTANCE)
            23. [Icon] Left icon (INSTANCE)
              24. [Element] Vector (VECTOR)
            25. [Label] Button (TEXT)
            26. [Icon] Right icon (INSTANCE)
              27. [Element] Vector (VECTOR)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Overlay=true | itemSpacing | `10px` | `—` | `—` |
| Overlay | fill | `#000000` | `—` | `—` |
| Overlay | itemSpacing | `10px` | `—` | `—` |
| bg | fill | `#000000` | `—` | `—` |
| Drawer Wrapper | fill | `#FFFFFF` | `drawer.background` | `var(--ach-drawer-background)` |
| .Drawer Header | stroke | `#DCDCDC` | `drawer.border` | `var(--ach-drawer-border)` |
| .Drawer Header | paddingTop | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .Drawer Header | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .Drawer Header | paddingBottom | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .Drawer Header | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .Drawer Header | itemSpacing | `10px` | `—` | `—` |
| Content | itemSpacing | `175px` | `—` | `—` |
| Drawer Title | itemSpacing | `10px` | `—` | `—` |
| Drawer Title | fill | `#262626` | `drawer.title-text` | `var(--ach-drawer-title-text)` |
| Drawer Title | fontSize | `20px` | `—` | `—` |
| Icons/ui-actions/close | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `drawer.icon` | `var(--ach-drawer-icon)` |
| Drawer Content | paddingTop | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Drawer Content | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Drawer Content | paddingBottom | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Drawer Content | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .Drawer Footer | stroke | `#DCDCDC` | `drawer.border` | `var(--ach-drawer-border)` |
| .Drawer Footer | paddingTop | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .Drawer Footer | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .Drawer Footer | paddingBottom | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .Drawer Footer | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .Drawer Footer | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Button Group | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 Button Outlined v1.1 | stroke | `#BDBDBD` | `button.outlined.neutral.border` | `var(--ach-button-outlined-neutral-border)` |
| 02 Button Outlined v1.1 | cornerRadius | `9999px` | `borderRadius.infinite` | `var(--ach-borderRadius-infinite)` |
| 02 Button Outlined v1.1 | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 Button Outlined v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Button Outlined v1.1 | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 Button Outlined v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Button Outlined v1.1 | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Left icon | fill | `#262626` | `button.outlined.neutral.text` | `var(--ach-button-outlined-neutral-text)` |
| Vector | fill | `#262626` | `button.outlined.neutral.text` | `var(--ach-button-outlined-neutral-text)` |
| Button | fill | `#262626` | `button.outlined.neutral.text` | `var(--ach-button-outlined-neutral-text)` |
| Button | fontSize | `14px` | `—` | `—` |
| Right icon | fill | `#262626` | `button.outlined.neutral.text` | `var(--ach-button-outlined-neutral-text)` |
| Vector | fill | `#262626` | `button.outlined.neutral.text` | `var(--ach-button-outlined-neutral-text)` |
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
id: .drawer-header
name: .DrawerHeader
category: layout
figma_component_name: ".Drawer Header"
figma_url: "https://www.figma.com/design//?node-id=1103-1263"
status: draft
tokens_used:
  - drawer.border
  - padding.4
  - drawer.title-text
  - drawer.icon
parent_components:
  - drawer
---

# .DrawerHeader

## Relationships

**Parent components (this component is used inside):**
- [`Drawer`](./drawer.component.md)

## Code contract

```typescript
interface .DrawerHeaderProps {
  /** Visual variant: Size */
  Size?: 'L' | 'M' | 'S';
  /** Visual variant: Title */
  Title?: 'False' | 'True';
  children?: React.ReactNode;
  className?: string;
}
```

## Usage

> This component is designed to be used inside [`Drawer`](./drawer.component.md).

```tsx
<Drawer>
  <.DrawerHeader />
  <.DrawerHeader />
</Drawer>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Size | `L`, `M`, `S` | `L` | Visual variant: Size |
| Title | `False`, `True` | `True` | Visual variant: Title |

## Anatomy

```
1. [Root] Size=L, Title=True (COMPONENT)
  2. [Container] Content (SLOT)
    3. [Container] Drawer Title (FRAME)
      4. [Label] Drawer Title (TEXT)
    5. [Icon] Icons/ui-actions/close (INSTANCE)
      6. [Element] Vector (VECTOR)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Size=L, Title=True | stroke | `#DCDCDC` | `drawer.border` | `var(--ach-drawer-border)` |
| Size=L, Title=True | paddingTop | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Size=L, Title=True | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Size=L, Title=True | paddingBottom | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Size=L, Title=True | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Size=L, Title=True | itemSpacing | `10px` | `—` | `—` |
| Content | itemSpacing | `175px` | `—` | `—` |
| Drawer Title | itemSpacing | `10px` | `—` | `—` |
| Drawer Title | fill | `#262626` | `drawer.title-text` | `var(--ach-drawer-title-text)` |
| Drawer Title | fontSize | `28px` | `—` | `—` |
| Icons/ui-actions/close | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `drawer.icon` | `var(--ach-drawer-icon)` |

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
id: .drawer-footer
name: .DrawerFooter
category: layout
figma_component_name: ".Drawer Footer"
figma_url: "https://www.figma.com/design//?node-id=1103-1301"
status: draft
tokens_used:
  - drawer.border
  - padding.4
  - padding.1
  - padding.2
  - button.outlined.neutral.border
  - borderRadius.infinite
  - button.outlined.neutral.text
  - button.primary.background
  - button.primary.text
parent_components:
  - drawer
---

# .DrawerFooter

## Relationships

**Parent components (this component is used inside):**
- [`Drawer`](./drawer.component.md)

## Code contract

```typescript
interface .DrawerFooterProps {
  /** Visual variant: Type */
  Type?: '2 Button Right' | '2 Full-width Button' | 'Single Full-width Button';
  children?: React.ReactNode;
  className?: string;
}
```

## Usage

> This component is designed to be used inside [`Drawer`](./drawer.component.md).

```tsx
<Drawer>
  <.DrawerFooter />
  <.DrawerFooter />
</Drawer>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Type | `2 Button Right`, `2 Full-width Button`, `Single Full-width Button` | `2 Button Right` | Visual variant: Type |

## Anatomy

```
1. [Root] Type=2 Button Right (COMPONENT)
  2. [Container] Content (SLOT)
    3. [Container] Button Group (FRAME)
      4. [Container] 02 Button Outlined v1.1 (INSTANCE)
        5. [Icon] Left icon (INSTANCE)
          6. [Element] Vector (VECTOR)
        7. [Label] Button (TEXT)
        8. [Icon] Right icon (INSTANCE)
          9. [Element] Vector (VECTOR)
      10. [Container] 01 Button Solid  v1.1 (INSTANCE)
        11. [Icon] Left icon (INSTANCE)
          12. [Element] Vector (VECTOR)
        13. [Label] Button (TEXT)
        14. [Icon] Right icon (INSTANCE)
          15. [Element] Vector (VECTOR)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Type=2 Button Right | stroke | `#DCDCDC` | `drawer.border` | `var(--ach-drawer-border)` |
| Type=2 Button Right | paddingTop | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Type=2 Button Right | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Type=2 Button Right | paddingBottom | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Type=2 Button Right | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Type=2 Button Right | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Button Group | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 Button Outlined v1.1 | stroke | `#BDBDBD` | `button.outlined.neutral.border` | `var(--ach-button-outlined-neutral-border)` |
| 02 Button Outlined v1.1 | cornerRadius | `9999px` | `borderRadius.infinite` | `var(--ach-borderRadius-infinite)` |
| 02 Button Outlined v1.1 | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 Button Outlined v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Button Outlined v1.1 | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 Button Outlined v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Button Outlined v1.1 | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Left icon | fill | `#262626` | `button.outlined.neutral.text` | `var(--ach-button-outlined-neutral-text)` |
| Vector | fill | `#262626` | `button.outlined.neutral.text` | `var(--ach-button-outlined-neutral-text)` |
| Button | fill | `#262626` | `button.outlined.neutral.text` | `var(--ach-button-outlined-neutral-text)` |
| Button | fontSize | `14px` | `—` | `—` |
| Right icon | fill | `#262626` | `button.outlined.neutral.text` | `var(--ach-button-outlined-neutral-text)` |
| Vector | fill | `#262626` | `button.outlined.neutral.text` | `var(--ach-button-outlined-neutral-text)` |
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
