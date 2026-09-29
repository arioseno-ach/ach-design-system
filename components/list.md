---
id: list-item
name: ListItem
category: layout
figma_component_name: "List Item"
figma_url: "https://www.figma.com/design//?node-id=1424-296"
status: draft
tokens_used:
  - list.item.background
  - padding.2
  - padding.4
  - icon.ach-color-icon-default
  - list.item.primary-text
  - list.item.secondary-text
  - divider.default
parent_components:
  - list
---

# ListItem

> An individual row within a List, containing content, text, and optional actions or icons.
AKA: List Row, List Entry, List Cell, Menu Item, List Tile

## Relationships

**Parent components (this component is used inside):**
- [`List`](./list.component.md)

## Code contract

```typescript
interface ListItemProps {
  /** Toggle: Show Left Icon */
  Show Left Icon?: boolean;
  /** Toggle: Show Right Icon */
  Show Right Icon?: boolean;
  /** Toggle: Bordered */
  Bordered?: boolean;
  /** Toggle: Show Supporting Text */
  Show Supporting Text?: boolean;
  /** Text content: Title */
  Title?: React.ReactNode;
  /** Text content: Supporting Text */
  Supporting Text?: React.ReactNode;
  /** Visual variant: Subtitle Direction */
  Subtitle Direction?: 'Vertical' | 'Horizontal';
  /** Visual variant: Size */
  Size?: 'S' | 'M' | 'L';
  /** Visual variant: Subtitle Role */
  Subtitle Role?: 'Supporting' | 'Value';
  children?: React.ReactNode;
  className?: string;
}
```

## Usage

> This component is designed to be used inside [`List`](./list.component.md).

```tsx
<List>
  <ListItem />
  <ListItem />
</List>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Subtitle Direction | `Vertical`, `Horizontal` | `Vertical` | Visual variant: Subtitle Direction |
| Size | `S`, `M`, `L` | `S` | Visual variant: Size |
| Subtitle Role | `Supporting`, `Value` | `Supporting` | Visual variant: Subtitle Role |

## Anatomy

```
1. [Root] Subtitle Direction=Vertical, Size=S, Subtitle Role=Supporting (COMPONENT)
  2. [Icon] Left Icon Slot (SLOT)
    3. [Icon] Icon (INSTANCE)
      4. [Element] Vector (VECTOR)
  5. [Container] Content (FRAME)
    6. [Label] Title (TEXT)
    7. [Label] Subtitle (TEXT)
  8. [Icon] Right Icon Slot (SLOT)
    9. [Icon] Icon (INSTANCE)
      10. [Element] Vector (VECTOR)
  11. [Divider] 01 Divider (INSTANCE)
    12. [Divider] Divider (RECTANGLE)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Subtitle Direction=Vertical, Size=S, Subtitle Role=Supporting | fill | `#FFFFFF` | `list.item.background` | `var(--ach-list-item-background)` |
| Subtitle Direction=Vertical, Size=S, Subtitle Role=Supporting | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Subtitle Direction=Vertical, Size=S, Subtitle Role=Supporting | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Subtitle Direction=Vertical, Size=S, Subtitle Role=Supporting | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Subtitle Direction=Vertical, Size=S, Subtitle Role=Supporting | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Subtitle Direction=Vertical, Size=S, Subtitle Role=Supporting | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `icon.ach-color-icon-default` | `var(--ach-icon-ach-color-icon-default)` |
| Content | itemSpacing | `2px` | `—` | `—` |
| Title | fill | `#262626` | `list.item.primary-text` | `var(--ach-list-item-primary-text)` |
| Title | fontSize | `12px` | `—` | `—` |
| Subtitle | fill | `#525252` | `list.item.secondary-text` | `var(--ach-list-item-secondary-text)` |
| Subtitle | fontSize | `12px` | `—` | `—` |
| Right Icon Slot | itemSpacing | `10px` | `—` | `—` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `icon.ach-color-icon-default` | `var(--ach-icon-ach-color-icon-default)` |
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


---

---
id: list
name: List
category: layout
figma_component_name: "List"
figma_url: "https://www.figma.com/design//?node-id=1607-32678"
status: draft
tokens_used:
  - list.background
  - list.item.background
  - padding.2
  - padding.4
  - icon.ach-color-icon-default
  - list.item.primary-text
  - list.item.secondary-text
  - divider.default
child_components:
  - list-item
---

# List

> A vertical container that displays a series of related items in a structured column.
AKA: List View, Item List, Content List, Stack List, Vertical List

## Relationships

**Child components (used inside this component):**
- [`List Item`](./list-item.component.md)

## Code contract

```typescript
interface ListProps {
  /** Visual variant: Orientation */
  Orientation?: 'Vertical' | 'Horizontal';
  children?: React.ReactNode; // Accepts: List Item
  className?: string;
}
```

## Usage

```tsx
<List>
  <ListItem />
  <ListItem />
</List>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Orientation | `Vertical`, `Horizontal` | `Vertical` | Visual variant: Orientation |

## Anatomy

```
1. [Root] Orientation=Vertical (COMPONENT)
  2. [Container] Items Slot (SLOT)
    3. [Container] 02 List Item (INSTANCE)
      4. [Icon] Left Icon Slot (SLOT)
        5. [Icon] Icon (INSTANCE)
          6. [Element] Vector (VECTOR)
      7. [Container] Content (FRAME)
        8. [Label] Title (TEXT)
        9. [Label] Subtitle (TEXT)
      10. [Icon] Right Icon Slot (SLOT)
        11. [Icon] Icon (INSTANCE)
          12. [Element] Vector (VECTOR)
      13. [Divider] 01 Divider (INSTANCE)
        14. [Divider] Divider (RECTANGLE)
    15. [Container] 02 List Item (INSTANCE)
      16. [Icon] Left Icon Slot (SLOT)
        17. [Icon] Icon (INSTANCE)
          18. [Element] Vector (VECTOR)
      19. [Container] Content (FRAME)
        20. [Label] Title (TEXT)
        21. [Label] Subtitle (TEXT)
      22. [Icon] Right Icon Slot (SLOT)
        23. [Icon] Icon (INSTANCE)
          24. [Element] Vector (VECTOR)
      25. [Divider] 01 Divider (INSTANCE)
        26. [Divider] Divider (RECTANGLE)
    27. [Container] 02 List Item (INSTANCE)
      28. [Icon] Left Icon Slot (SLOT)
        29. [Icon] Icon (INSTANCE)
          30. [Element] Vector (VECTOR)
      31. [Container] Content (FRAME)
        32. [Label] Title (TEXT)
        33. [Label] Subtitle (TEXT)
      34. [Icon] Right Icon Slot (SLOT)
        35. [Icon] Icon (INSTANCE)
          36. [Element] Vector (VECTOR)
      37. [Divider] 01 Divider (INSTANCE)
        38. [Divider] Divider (RECTANGLE)
    39. [Container] 02 List Item (INSTANCE)
      40. [Icon] Left Icon Slot (SLOT)
        41. [Icon] Icon (INSTANCE)
          42. [Element] Vector (VECTOR)
      43. [Container] Content (FRAME)
        44. [Label] Title (TEXT)
        45. [Label] Subtitle (TEXT)
      46. [Icon] Right Icon Slot (SLOT)
        47. [Icon] Icon (INSTANCE)
          48. [Element] Vector (VECTOR)
      49. [Divider] 01 Divider (INSTANCE)
        50. [Divider] Divider (RECTANGLE)
    51. [Container] 02 List Item (INSTANCE)
      52. [Icon] Left Icon Slot (SLOT)
        53. [Icon] Icon (INSTANCE)
          54. [Element] Vector (VECTOR)
      55. [Container] Content (FRAME)
        56. [Label] Title (TEXT)
        57. [Label] Subtitle (TEXT)
      58. [Icon] Right Icon Slot (SLOT)
        59. [Icon] Icon (INSTANCE)
          60. [Element] Vector (VECTOR)
      61. [Divider] 01 Divider (INSTANCE)
        62. [Divider] Divider (RECTANGLE)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Orientation=Vertical | fill | `#FFFFFF` | `list.background` | `var(--ach-list-background)` |
| 02 List Item | fill | `#FFFFFF` | `list.item.background` | `var(--ach-list-item-background)` |
| 02 List Item | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 List Item | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 List Item | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 List Item | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 List Item | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `icon.ach-color-icon-default` | `var(--ach-icon-ach-color-icon-default)` |
| Content | itemSpacing | `2px` | `—` | `—` |
| Title | fill | `#262626` | `list.item.primary-text` | `var(--ach-list-item-primary-text)` |
| Title | fontSize | `14px` | `—` | `—` |
| Subtitle | fill | `#525252` | `list.item.secondary-text` | `var(--ach-list-item-secondary-text)` |
| Subtitle | fontSize | `14px` | `—` | `—` |
| Right Icon Slot | itemSpacing | `10px` | `—` | `—` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `icon.ach-color-icon-default` | `var(--ach-icon-ach-color-icon-default)` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 List Item | fill | `#FFFFFF` | `list.item.background` | `var(--ach-list-item-background)` |
| 02 List Item | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 List Item | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 List Item | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 List Item | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 List Item | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `icon.ach-color-icon-default` | `var(--ach-icon-ach-color-icon-default)` |
| Content | itemSpacing | `2px` | `—` | `—` |
| Title | fill | `#262626` | `list.item.primary-text` | `var(--ach-list-item-primary-text)` |
| Title | fontSize | `14px` | `—` | `—` |
| Subtitle | fill | `#525252` | `list.item.secondary-text` | `var(--ach-list-item-secondary-text)` |
| Subtitle | fontSize | `14px` | `—` | `—` |
| Right Icon Slot | itemSpacing | `10px` | `—` | `—` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `icon.ach-color-icon-default` | `var(--ach-icon-ach-color-icon-default)` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 List Item | fill | `#FFFFFF` | `list.item.background` | `var(--ach-list-item-background)` |
| 02 List Item | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 List Item | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 List Item | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 List Item | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 List Item | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `icon.ach-color-icon-default` | `var(--ach-icon-ach-color-icon-default)` |
| Content | itemSpacing | `2px` | `—` | `—` |
| Title | fill | `#262626` | `list.item.primary-text` | `var(--ach-list-item-primary-text)` |
| Title | fontSize | `14px` | `—` | `—` |
| Subtitle | fill | `#525252` | `list.item.secondary-text` | `var(--ach-list-item-secondary-text)` |
| Subtitle | fontSize | `14px` | `—` | `—` |
| Right Icon Slot | itemSpacing | `10px` | `—` | `—` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `icon.ach-color-icon-default` | `var(--ach-icon-ach-color-icon-default)` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 List Item | fill | `#FFFFFF` | `list.item.background` | `var(--ach-list-item-background)` |
| 02 List Item | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 List Item | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 List Item | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 List Item | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 List Item | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `icon.ach-color-icon-default` | `var(--ach-icon-ach-color-icon-default)` |
| Content | itemSpacing | `2px` | `—` | `—` |
| Title | fill | `#262626` | `list.item.primary-text` | `var(--ach-list-item-primary-text)` |
| Title | fontSize | `14px` | `—` | `—` |
| Subtitle | fill | `#525252` | `list.item.secondary-text` | `var(--ach-list-item-secondary-text)` |
| Subtitle | fontSize | `14px` | `—` | `—` |
| Right Icon Slot | itemSpacing | `10px` | `—` | `—` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `icon.ach-color-icon-default` | `var(--ach-icon-ach-color-icon-default)` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 List Item | fill | `#FFFFFF` | `list.item.background` | `var(--ach-list-item-background)` |
| 02 List Item | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 List Item | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 List Item | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 List Item | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 List Item | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `icon.ach-color-icon-default` | `var(--ach-icon-ach-color-icon-default)` |
| Content | itemSpacing | `2px` | `—` | `—` |
| Title | fill | `#262626` | `list.item.primary-text` | `var(--ach-list-item-primary-text)` |
| Title | fontSize | `14px` | `—` | `—` |
| Subtitle | fill | `#525252` | `list.item.secondary-text` | `var(--ach-list-item-secondary-text)` |
| Subtitle | fontSize | `14px` | `—` | `—` |
| Right Icon Slot | itemSpacing | `10px` | `—` | `—` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `icon.ach-color-icon-default` | `var(--ach-icon-ach-color-icon-default)` |
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
