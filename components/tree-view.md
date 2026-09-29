---
id: tree-navigation
name: TreeNavigation
category: navigation
figma_component_name: "Tree Navigation"
figma_url: "https://www.figma.com/design//?node-id=1936-56"
status: draft
tokens_used:
  - treeview.treenavigation.background
  - padding.2
  - treeview.item.background
  - borderRadius.sm
  - spacing.1-5
  - treeview.item.icon
  - treeview.item.text
  - padding.8
  - treeview.item.connector
  - treeview.item.text_child
  - padding.14
child_components:
  - tree-item
---

# TreeNavigation

> A hierarchical navigation component displaying nested items in an expandable tree structure.
AKA: Tree View, File Tree, Directory Tree, Nested Navigation, Hierarchy View, Folder Tree

## Relationships

**Child components (used inside this component):**
- [`Tree Item`](./tree-item.component.md)

## Code contract

```typescript
interface TreeNavigationProps {
  children?: React.ReactNode; // Accepts: Tree Item
  className?: string;
}
```

## Usage

```tsx
<TreeNavigation>
  <TreeItem />
  <TreeItem />
</TreeNavigation>
```

## Anatomy

```
1. [Root] 01 Tree Navigation (COMPONENT)
  2. [Container] Tree Items (SLOT)
    3. [Container] Tree Item (INSTANCE)
      4. [Icon] Leading Icon (INSTANCE)
        5. [Element] Vector (VECTOR)
      6. [Label] Label (TEXT)
      7. [Container] Chevron Container (FRAME)
        8. [Element] Chevron (INSTANCE)
          9. [Element] Vector (VECTOR)
    10. [Container] Tree Item (INSTANCE)
      11. [Element] Connector (RECTANGLE)
      12. [Icon] Leading Icon (INSTANCE)
        13. [Element] Vector (VECTOR)
      14. [Label] Label (TEXT)
      15. [Container] Chevron Container (FRAME)
        16. [Element] Chevron (INSTANCE)
          17. [Element] Vector (VECTOR)
    18. [Container] Tree Item (INSTANCE)
      19. [Element] Connector (RECTANGLE)
      20. [Icon] Leading Icon (INSTANCE)
        21. [Element] Vector (VECTOR)
      22. [Label] Label (TEXT)
      23. [Container] Chevron Container (FRAME)
        24. [Element] Chevron (INSTANCE)
          25. [Element] Vector (VECTOR)
    26. [Container] Tree Item (INSTANCE)
      27. [Element] Connector (RECTANGLE)
      28. [Icon] Leading Icon (INSTANCE)
        29. [Element] Vector (VECTOR)
      30. [Label] Label (TEXT)
      31. [Container] Chevron Container (FRAME)
        32. [Element] Chevron (INSTANCE)
          33. [Element] Vector (VECTOR)
    34. [Container] Tree Item (INSTANCE)
      35. [Icon] Leading Icon (INSTANCE)
        36. [Element] Vector (VECTOR)
      37. [Label] Label (TEXT)
      38. [Container] Chevron Container (FRAME)
        39. [Element] Chevron (INSTANCE)
          40. [Element] Vector (VECTOR)
    41. [Container] Tree Item (INSTANCE)
      42. [Icon] Leading Icon (INSTANCE)
        43. [Element] Vector (VECTOR)
      44. [Label] Label (TEXT)
      45. [Container] Chevron Container (FRAME)
        46. [Element] Chevron (INSTANCE)
          47. [Element] Vector (VECTOR)
    48. [Container] Tree Item (INSTANCE)
      49. [Icon] Leading Icon (INSTANCE)
        50. [Element] Vector (VECTOR)
      51. [Label] Label (TEXT)
      52. [Container] Chevron Container (FRAME)
        53. [Element] Chevron (INSTANCE)
          54. [Element] Vector (VECTOR)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| 01 Tree Navigation | fill | `#FFFFFF` | `treeview.treenavigation.background` | `var(--ach-treeview-treenavigation-background)` |
| 01 Tree Navigation | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 01 Tree Navigation | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Tree Item | fill | `#FFFFFF` | `treeview.item.background` | `var(--ach-treeview-item-background)` |
| Tree Item | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Tree Item | paddingTop | `6px` | `spacing.1-5` | `var(--ach-spacing-1-5)` |
| Tree Item | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Tree Item | paddingBottom | `6px` | `spacing.1-5` | `var(--ach-spacing-1-5)` |
| Tree Item | paddingLeft | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Tree Item | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Vector | fill | `#262626` | `treeview.item.icon` | `var(--ach-treeview-item-icon)` |
| Label | fill | `#262626` | `treeview.item.text` | `var(--ach-treeview-item-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Chevron | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `treeview.item.icon` | `var(--ach-treeview-item-icon)` |
| Tree Item | fill | `#FFFFFF` | `treeview.item.background` | `var(--ach-treeview-item-background)` |
| Tree Item | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Tree Item | paddingTop | `6px` | `spacing.1-5` | `var(--ach-spacing-1-5)` |
| Tree Item | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Tree Item | paddingBottom | `6px` | `spacing.1-5` | `var(--ach-spacing-1-5)` |
| Tree Item | paddingLeft | `32px` | `padding.8` | `var(--ach-padding-8)` |
| Tree Item | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Connector | fill | `#EEEEEE` | `treeview.item.connector` | `var(--ach-treeview-item-connector)` |
| Vector | fill | `#262626` | `treeview.item.icon` | `var(--ach-treeview-item-icon)` |
| Label | fill | `#525252` | `treeview.item.text_child` | `var(--ach-treeview-item-text_child)` |
| Label | fontSize | `14px` | `—` | `—` |
| Chevron | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `treeview.item.icon` | `var(--ach-treeview-item-icon)` |
| Tree Item | fill | `#FFFFFF` | `treeview.item.background` | `var(--ach-treeview-item-background)` |
| Tree Item | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Tree Item | paddingTop | `6px` | `spacing.1-5` | `var(--ach-spacing-1-5)` |
| Tree Item | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Tree Item | paddingBottom | `6px` | `spacing.1-5` | `var(--ach-spacing-1-5)` |
| Tree Item | paddingLeft | `32px` | `padding.8` | `var(--ach-padding-8)` |
| Tree Item | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Connector | fill | `#EEEEEE` | `treeview.item.connector` | `var(--ach-treeview-item-connector)` |
| Vector | fill | `#262626` | `treeview.item.icon` | `var(--ach-treeview-item-icon)` |
| Label | fill | `#525252` | `treeview.item.text_child` | `var(--ach-treeview-item-text_child)` |
| Label | fontSize | `14px` | `—` | `—` |
| Chevron | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `treeview.item.icon` | `var(--ach-treeview-item-icon)` |
| Tree Item | fill | `#FFFFFF` | `treeview.item.background` | `var(--ach-treeview-item-background)` |
| Tree Item | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Tree Item | paddingTop | `6px` | `spacing.1-5` | `var(--ach-spacing-1-5)` |
| Tree Item | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Tree Item | paddingBottom | `6px` | `spacing.1-5` | `var(--ach-spacing-1-5)` |
| Tree Item | paddingLeft | `56px` | `padding.14` | `var(--ach-padding-14)` |
| Tree Item | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Connector | fill | `#EEEEEE` | `treeview.item.connector` | `var(--ach-treeview-item-connector)` |
| Vector | fill | `#262626` | `treeview.item.icon` | `var(--ach-treeview-item-icon)` |
| Label | fill | `#525252` | `treeview.item.text_child` | `var(--ach-treeview-item-text_child)` |
| Label | fontSize | `14px` | `—` | `—` |
| Chevron | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `treeview.item.icon` | `var(--ach-treeview-item-icon)` |
| Tree Item | fill | `#FFFFFF` | `treeview.item.background` | `var(--ach-treeview-item-background)` |
| Tree Item | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Tree Item | paddingTop | `6px` | `spacing.1-5` | `var(--ach-spacing-1-5)` |
| Tree Item | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Tree Item | paddingBottom | `6px` | `spacing.1-5` | `var(--ach-spacing-1-5)` |
| Tree Item | paddingLeft | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Tree Item | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Vector | fill | `#262626` | `treeview.item.icon` | `var(--ach-treeview-item-icon)` |
| Label | fill | `#262626` | `treeview.item.text` | `var(--ach-treeview-item-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Chevron | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `treeview.item.icon` | `var(--ach-treeview-item-icon)` |
| Tree Item | fill | `#FFFFFF` | `treeview.item.background` | `var(--ach-treeview-item-background)` |
| Tree Item | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Tree Item | paddingTop | `6px` | `spacing.1-5` | `var(--ach-spacing-1-5)` |
| Tree Item | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Tree Item | paddingBottom | `6px` | `spacing.1-5` | `var(--ach-spacing-1-5)` |
| Tree Item | paddingLeft | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Tree Item | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Vector | fill | `#262626` | `treeview.item.icon` | `var(--ach-treeview-item-icon)` |
| Label | fill | `#262626` | `treeview.item.text` | `var(--ach-treeview-item-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Chevron | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `treeview.item.icon` | `var(--ach-treeview-item-icon)` |
| Tree Item | fill | `#FFFFFF` | `treeview.item.background` | `var(--ach-treeview-item-background)` |
| Tree Item | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Tree Item | paddingTop | `6px` | `spacing.1-5` | `var(--ach-spacing-1-5)` |
| Tree Item | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Tree Item | paddingBottom | `6px` | `spacing.1-5` | `var(--ach-spacing-1-5)` |
| Tree Item | paddingLeft | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Tree Item | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Vector | fill | `#262626` | `treeview.item.icon` | `var(--ach-treeview-item-icon)` |
| Label | fill | `#262626` | `treeview.item.text` | `var(--ach-treeview-item-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Chevron | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `treeview.item.icon` | `var(--ach-treeview-item-icon)` |

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
id: tree-item
name: TreeItem
category: primitive
figma_component_name: "Tree Item"
figma_url: "https://www.figma.com/design//?node-id=1940-288"
status: draft
tokens_used:
  - treeview.item.background
  - borderRadius.sm
  - spacing.1-5
  - padding.2
  - treeview.item.icon
  - treeview.item.text
parent_components:
  - tree-navigation
---

# TreeItem

> An individual node within a Tree Navigation, with expand/collapse and selection states.
AKA: Tree Node, Tree Leaf, Tree Branch, Nested Item, Hierarchy Item

## Relationships

**Parent components (this component is used inside):**
- [`Tree Navigation`](./tree-navigation.component.md)

## Code contract

```typescript
interface TreeItemProps {
  /** Toggle: Has Icon */
  Has Icon?: boolean;
  /** Toggle: Has Children */
  Has Children?: boolean;
  /** Text content: Label */
  Label?: React.ReactNode;
  /** Visual variant: State */
  State?: 'Default' | 'Hover' | 'Selected' | 'Disabled';
  /** Visual variant: Expanded */
  Expanded?: 'True' | 'False';
  /** Visual variant: Level */
  Level?: '1' | '2' | '3';
  children?: React.ReactNode;
  className?: string;
}
```

## Usage

> This component is designed to be used inside [`Tree Navigation`](./tree-navigation.component.md).

```tsx
<TreeNavigation>
  <TreeItem />
  <TreeItem />
</TreeNavigation>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| State | `Default`, `Hover`, `Selected`, `Disabled` | `Default` | Visual variant: State |
| Expanded | `True`, `False` | `True` | Visual variant: Expanded |
| Level | `1`, `2`, `3` | `1` | Visual variant: Level |

## Anatomy

```
1. [Root] State=Default, Expanded=True, Level=1 (COMPONENT)
  2. [Icon] Leading Icon (INSTANCE)
    3. [Element] Vector (VECTOR)
  4. [Label] Label (TEXT)
  5. [Container] Chevron Container (FRAME)
    6. [Element] Chevron (INSTANCE)
      7. [Element] Vector (VECTOR)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| State=Default, Expanded=True, Level=1 | fill | `#FFFFFF` | `treeview.item.background` | `var(--ach-treeview-item-background)` |
| State=Default, Expanded=True, Level=1 | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| State=Default, Expanded=True, Level=1 | paddingTop | `6px` | `spacing.1-5` | `var(--ach-spacing-1-5)` |
| State=Default, Expanded=True, Level=1 | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| State=Default, Expanded=True, Level=1 | paddingBottom | `6px` | `spacing.1-5` | `var(--ach-spacing-1-5)` |
| State=Default, Expanded=True, Level=1 | paddingLeft | `8px` | `padding.2` | `var(--ach-padding-2)` |
| State=Default, Expanded=True, Level=1 | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Vector | fill | `#262626` | `treeview.item.icon` | `var(--ach-treeview-item-icon)` |
| Label | fill | `#262626` | `treeview.item.text` | `var(--ach-treeview-item-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Chevron | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `treeview.item.icon` | `var(--ach-treeview-item-icon)` |

## States

| State | Present | Notes |
| :--- | :--- | :--- |
| Default | ✅ | Defined in Figma |
| Hover | ✅ | Defined in Figma |
| Pressed | ❌ | Not found — add variant or document manually |
| Focus | ❌ | Not found — add variant or document manually |
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
