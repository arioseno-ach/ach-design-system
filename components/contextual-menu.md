---
id: contextual-menu-item
name: ContextualMenuItem
category: navigation
figma_component_name: "Contextual Menu Item"
figma_url: "https://www.figma.com/design//?node-id=272-3489"
status: draft
tokens_used:
  - borderRadius.xs
  - padding.4
  - padding.3
  - Color
  - 3xs
  - contextual-menu.item.icon
  - contextual-menu.item.text
  - contextual-menu.item.text-secondary
parent_components:
  - contextual-menu-v1.1
---

# ContextualMenuItem

> An individual menu item within a Contextual Menu, representing a single action or option.
AKA: Menu Item, Dropdown Item, Option, Action Item, List Action

## Relationships

**Parent components (this component is used inside):**
- [`Contextual Menu v1.1`](./contextual-menu-v1.1.component.md)

## Code contract

```typescript
interface ContextualMenuItemProps {
  /** Toggle: Show left decoration */
  Show left decoration?: boolean;
  /** Toggle: Show right decoration */
  Show right decoration?: boolean;
  /** Toggle: Show line 2 */
  Show line 2?: boolean;
  /** Visual variant: State */
  State?: 'Default' | 'Hover' | 'Focus' | 'Active' | 'Selected' | 'Disabled';
  children?: React.ReactNode;
  className?: string;
}
```

## Usage

> This component is designed to be used inside [`Contextual Menu v1.1`](./contextual-menu-v1.1.component.md).

```tsx
<ContextualMenuV1.1>
  <ContextualMenuItem />
  <ContextualMenuItem />
</ContextualMenuV1.1>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| State | `Default`, `Hover`, `Focus`, `Active`, `Selected`, `Disabled` | `Default` | Visual variant: State |

## Anatomy

```
1. [Root] State=Default (COMPONENT)
  2. [Container] Left decoration (INSTANCE)
    3. [Icon] Icon (INSTANCE)
      4. [Element] Vector (VECTOR)
  5. [Container] Content (FRAME)
    6. [Label] Label (TEXT)
    7. [Label] Line 2 (TEXT)
  8. [Container] Right decoration (INSTANCE)
    9. [Icon] Icon (INSTANCE)
      10. [Element] Vector (VECTOR)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| State=Default | cornerRadius | `4px` | `borderRadius.xs` | `var(--ach-borderRadius-xs)` |
| State=Default | paddingTop | `16px` | `padding.4` | `var(--ach-padding-4)` |
| State=Default | paddingRight | `12px` | `padding.3` | `var(--ach-padding-3)` |
| State=Default | paddingBottom | `16px` | `padding.4` | `var(--ach-padding-4)` |
| State=Default | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| State=Default | itemSpacing | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Left decoration | fill | `#FFFFFF` | `Color` | `var(--ach-Color)` |
| Left decoration | paddingTop | `2px` | `3xs` | `var(--ach-3xs)` |
| Left decoration | paddingRight | `2px` | `3xs` | `var(--ach-3xs)` |
| Left decoration | paddingBottom | `2px` | `3xs` | `var(--ach-3xs)` |
| Left decoration | paddingLeft | `2px` | `3xs` | `var(--ach-3xs)` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `contextual-menu.item.icon` | `var(--ach-contextual-menu-item-icon)` |
| Label | fill | `#262626` | `contextual-menu.item.text` | `var(--ach-contextual-menu-item-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Line 2 | fill | `#525252` | `contextual-menu.item.text-secondary` | `var(--ach-contextual-menu-item-text-secondary)` |
| Line 2 | fontSize | `12px` | `—` | `—` |
| Right decoration | paddingTop | `2px` | `3xs` | `var(--ach-3xs)` |
| Right decoration | paddingRight | `2px` | `3xs` | `var(--ach-3xs)` |
| Right decoration | paddingBottom | `2px` | `3xs` | `var(--ach-3xs)` |
| Right decoration | paddingLeft | `2px` | `3xs` | `var(--ach-3xs)` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `contextual-menu.item.icon` | `var(--ach-contextual-menu-item-icon)` |

## States

| State | Present | Notes |
| :--- | :--- | :--- |
| Default | ✅ | Defined in Figma |
| Hover | ✅ | Defined in Figma |
| Pressed | ✅ | Defined in Figma |
| Focus | ✅ | Defined in Figma |
| Disabled | ✅ | Defined in Figma |
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
id: contextual-menu-group-label
name: ContextualMenuGroupLabel
category: navigation
figma_component_name: "Contextual Menu Group Label"
figma_url: "https://www.figma.com/design//?node-id=272-3689"
status: draft
tokens_used:
  - padding.2
  - contextual-menu.group-label.text
---

# ContextualMenuGroupLabel

> A label used to group related items within a Contextual Menu.
AKA: Menu Section Label, Group Header, Menu Divider Label, Section Title

## Code contract

```typescript
interface ContextualMenuGroupLabelProps {
  /** Visual variant: Type */
  Type?: 'Small' | 'Regular';
  /** Visual variant: Indented? */
  Indented??: 'False' | 'True';
  children?: React.ReactNode;
  className?: string;
}
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Type | `Small`, `Regular` | `Small` | Visual variant: Type |
| Indented? | `False`, `True` | `False` | Visual variant: Indented? |

## Anatomy

```
1. [Root] Type=Small, Indented?=False (COMPONENT)
  2. [Label] Group label (TEXT)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Type=Small, Indented?=False | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Type=Small, Indented?=False | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Type=Small, Indented?=False | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Type=Small, Indented?=False | paddingLeft | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Type=Small, Indented?=False | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Group label | fill | `#737373` | `contextual-menu.group-label.text` | `var(--ach-contextual-menu-group-label-text)` |
| Group label | fontSize | `12px` | `—` | `—` |

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
id: contextual-menu-v1.1
name: ContextualMenuV1.1
category: navigation
figma_component_name: "Contextual Menu v1.1"
figma_url: "https://www.figma.com/design//?node-id=1167-995"
status: draft
tokens_used:
  - contextual-menu.background
  - contextual-menu.border
  - borderRadius.sm
  - padding.2
  - borderRadius.xs
  - padding.3
  - Color
  - 3xs
  - contextual-menu.item.icon
  - contextual-menu.item.text
  - contextual-menu.item.text-secondary
child_components:
  - contextual-menu-item
---

# ContextualMenuV1.1

> An list of menu item within a Contextual Menu, representing a single action or option.
AKA: Menu Item, Dropdown Item, Option, Action Item, List Action
Popup, Popover

## Relationships

**Child components (used inside this component):**
- [`Contextual Menu Item`](./contextual-menu-item.component.md)

## Code contract

```typescript
interface ContextualMenuV1.1Props {
  /** Visual variant: Spacing */
  Spacing?: 'None';
  children?: React.ReactNode; // Accepts: Contextual Menu Item
  className?: string;
}
```

## Usage

```tsx
<ContextualMenuV1.1>
  <ContextualMenuItem />
  <ContextualMenuItem />
</ContextualMenuV1.1>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Spacing | `None` | `None` | Visual variant: Spacing |

## Anatomy

```
1. [Root] Spacing=None (COMPONENT)
  2. [Container] slot (SLOT)
    3. [Container] 02 Contextual Menu Item (INSTANCE)
      4. [Container] Left decoration (INSTANCE)
        5. [Icon] Icon (INSTANCE)
          6. [Element] Vector (VECTOR)
      7. [Container] Content (FRAME)
        8. [Label] Label (TEXT)
        9. [Label] Line 2 (TEXT)
      10. [Container] Right decoration (INSTANCE)
        11. [Icon] Icon (INSTANCE)
          12. [Element] Vector (VECTOR)
    13. [Container] 02 Contextual Menu Item (INSTANCE)
      14. [Container] Left decoration (INSTANCE)
        15. [Icon] Icon (INSTANCE)
          16. [Element] Vector (VECTOR)
      17. [Container] Content (FRAME)
        18. [Label] Label (TEXT)
        19. [Label] Line 2 (TEXT)
      20. [Container] Right decoration (INSTANCE)
        21. [Icon] Icon (INSTANCE)
          22. [Element] Vector (VECTOR)
    23. [Container] 02 Contextual Menu Item (INSTANCE)
      24. [Container] Left decoration (INSTANCE)
        25. [Icon] Icon (INSTANCE)
          26. [Element] Vector (VECTOR)
      27. [Container] Content (FRAME)
        28. [Label] Label (TEXT)
        29. [Label] Line 2 (TEXT)
      30. [Container] Right decoration (INSTANCE)
        31. [Icon] Icon (INSTANCE)
          32. [Element] Vector (VECTOR)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Spacing=None | fill | `#FFFFFF` | `contextual-menu.background` | `var(--ach-contextual-menu-background)` |
| Spacing=None | stroke | `#DCDCDC` | `contextual-menu.border` | `var(--ach-contextual-menu-border)` |
| Spacing=None | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Spacing=None | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 Contextual Menu Item | cornerRadius | `4px` | `borderRadius.xs` | `var(--ach-borderRadius-xs)` |
| 02 Contextual Menu Item | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 Contextual Menu Item | paddingRight | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 02 Contextual Menu Item | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 Contextual Menu Item | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 02 Contextual Menu Item | itemSpacing | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Left decoration | fill | `#FFFFFF` | `Color` | `var(--ach-Color)` |
| Left decoration | paddingTop | `2px` | `3xs` | `var(--ach-3xs)` |
| Left decoration | paddingRight | `2px` | `3xs` | `var(--ach-3xs)` |
| Left decoration | paddingBottom | `2px` | `3xs` | `var(--ach-3xs)` |
| Left decoration | paddingLeft | `2px` | `3xs` | `var(--ach-3xs)` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `contextual-menu.item.icon` | `var(--ach-contextual-menu-item-icon)` |
| Label | fill | `#262626` | `contextual-menu.item.text` | `var(--ach-contextual-menu-item-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Line 2 | fill | `#525252` | `contextual-menu.item.text-secondary` | `var(--ach-contextual-menu-item-text-secondary)` |
| Line 2 | fontSize | `12px` | `—` | `—` |
| Right decoration | paddingTop | `2px` | `3xs` | `var(--ach-3xs)` |
| Right decoration | paddingRight | `2px` | `3xs` | `var(--ach-3xs)` |
| Right decoration | paddingBottom | `2px` | `3xs` | `var(--ach-3xs)` |
| Right decoration | paddingLeft | `2px` | `3xs` | `var(--ach-3xs)` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `contextual-menu.item.icon` | `var(--ach-contextual-menu-item-icon)` |
| 02 Contextual Menu Item | cornerRadius | `4px` | `borderRadius.xs` | `var(--ach-borderRadius-xs)` |
| 02 Contextual Menu Item | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 Contextual Menu Item | paddingRight | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 02 Contextual Menu Item | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 Contextual Menu Item | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 02 Contextual Menu Item | itemSpacing | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Left decoration | fill | `#FFFFFF` | `Color` | `var(--ach-Color)` |
| Left decoration | paddingTop | `2px` | `3xs` | `var(--ach-3xs)` |
| Left decoration | paddingRight | `2px` | `3xs` | `var(--ach-3xs)` |
| Left decoration | paddingBottom | `2px` | `3xs` | `var(--ach-3xs)` |
| Left decoration | paddingLeft | `2px` | `3xs` | `var(--ach-3xs)` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `contextual-menu.item.icon` | `var(--ach-contextual-menu-item-icon)` |
| Label | fill | `#262626` | `contextual-menu.item.text` | `var(--ach-contextual-menu-item-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Line 2 | fill | `#525252` | `contextual-menu.item.text-secondary` | `var(--ach-contextual-menu-item-text-secondary)` |
| Line 2 | fontSize | `12px` | `—` | `—` |
| Right decoration | paddingTop | `2px` | `3xs` | `var(--ach-3xs)` |
| Right decoration | paddingRight | `2px` | `3xs` | `var(--ach-3xs)` |
| Right decoration | paddingBottom | `2px` | `3xs` | `var(--ach-3xs)` |
| Right decoration | paddingLeft | `2px` | `3xs` | `var(--ach-3xs)` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `contextual-menu.item.icon` | `var(--ach-contextual-menu-item-icon)` |
| 02 Contextual Menu Item | cornerRadius | `4px` | `borderRadius.xs` | `var(--ach-borderRadius-xs)` |
| 02 Contextual Menu Item | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 Contextual Menu Item | paddingRight | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 02 Contextual Menu Item | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 Contextual Menu Item | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 02 Contextual Menu Item | itemSpacing | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Left decoration | fill | `#FFFFFF` | `Color` | `var(--ach-Color)` |
| Left decoration | paddingTop | `2px` | `3xs` | `var(--ach-3xs)` |
| Left decoration | paddingRight | `2px` | `3xs` | `var(--ach-3xs)` |
| Left decoration | paddingBottom | `2px` | `3xs` | `var(--ach-3xs)` |
| Left decoration | paddingLeft | `2px` | `3xs` | `var(--ach-3xs)` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `contextual-menu.item.icon` | `var(--ach-contextual-menu-item-icon)` |
| Label | fill | `#262626` | `contextual-menu.item.text` | `var(--ach-contextual-menu-item-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Line 2 | fill | `#525252` | `contextual-menu.item.text-secondary` | `var(--ach-contextual-menu-item-text-secondary)` |
| Line 2 | fontSize | `12px` | `—` | `—` |
| Right decoration | paddingTop | `2px` | `3xs` | `var(--ach-3xs)` |
| Right decoration | paddingRight | `2px` | `3xs` | `var(--ach-3xs)` |
| Right decoration | paddingBottom | `2px` | `3xs` | `var(--ach-3xs)` |
| Right decoration | paddingLeft | `2px` | `3xs` | `var(--ach-3xs)` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `contextual-menu.item.icon` | `var(--ach-contextual-menu-item-icon)` |

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
