---
id: tab-segmented-item
name: TabSegmentedItem
category: navigation
figma_component_name: "Tab Segmented Item"
figma_url: "https://www.figma.com/design//?node-id=1296-65167"
status: draft
tokens_used:
  - borderRadius.sm
  - padding.1
  - padding.2
  - tabs.segmented.item.text_inactive
  - tabs.counter.background
  - radius
  - xs
  - tabs.counter.text
parent_components:
  - tabs-segemented
---

# TabSegmentedItem

> An individual tab within a Segmented Tab bar, with a contained/pill active state.
AKA: Segment, Segmented Tab, Pill Tab, Toggle Item, Segment Button

## Relationships

**Parent components (this component is used inside):**
- [`Tabs Segemented`](./tabs-segemented.component.md)

## Code contract

```typescript
interface TabSegmentedItemProps {
  /** Toggle: Show counter */
  Show counter?: boolean;
  /** Text content: Tab Label */
  Tab Label?: React.ReactNode;
  /** Slot: Icon */
  Icon?: React.ReactNode;
  /** Visual variant: Size */
  Size?: 'Regular' | 'Large' | 'Small';
  /** Visual variant: Content */
  Content?: 'Label' | 'Icon' | 'Icon + Label';
  /** Visual variant: State */
  State?: 'Inactive' | 'Hover' | 'Active' | 'Disabled';
  children?: React.ReactNode;
  className?: string;
}
```

## Usage

> This component is designed to be used inside [`Tabs Segemented`](./tabs-segemented.component.md).

```tsx
<TabsSegemented>
  <TabSegmentedItem />
  <TabSegmentedItem />
</TabsSegemented>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Size | `Regular`, `Large`, `Small` | `Regular` | Visual variant: Size |
| Content | `Label`, `Icon`, `Icon + Label` | `Label` | Visual variant: Content |
| State | `Inactive`, `Hover`, `Active`, `Disabled` | `Inactive` | Visual variant: State |

## Anatomy

```
1. [Root] Size=Regular, Content=Label, State=Inactive (COMPONENT)
  2. [Label] Label (TEXT)
  3. [Container] .Tab Counter (INSTANCE)
    4. [Label] 1 (TEXT)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Size=Regular, Content=Label, State=Inactive | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Size=Regular, Content=Label, State=Inactive | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Size=Regular, Content=Label, State=Inactive | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Size=Regular, Content=Label, State=Inactive | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Size=Regular, Content=Label, State=Inactive | paddingLeft | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Size=Regular, Content=Label, State=Inactive | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Label | fill | `#525252` | `tabs.segmented.item.text_inactive` | `var(--ach-tabs-segmented-item-text_inactive)` |
| Label | fontSize | `14px` | `—` | `—` |
| .Tab Counter | fill | `#EEEEEE` | `tabs.counter.background` | `var(--ach-tabs-counter-background)` |
| .Tab Counter | cornerRadius | `10px` | `radius` | `var(--ach-radius)` |
| .Tab Counter | itemSpacing | `8px` | `xs` | `var(--ach-xs)` |
| 1 | fill | `#262626` | `tabs.counter.text` | `var(--ach-tabs-counter-text)` |
| 1 | fontSize | `10px` | `—` | `—` |

## States

| State | Present | Notes |
| :--- | :--- | :--- |
| Default | ✅ | Defined in Figma |
| Hover | ✅ | Defined in Figma |
| Pressed | ✅ | Defined in Figma |
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


---

---
id: tabs-segemented
name: TabsSegemented
category: navigation
figma_component_name: "Tabs Segemented"
figma_url: "https://www.figma.com/design//?node-id=1297-24561"
status: draft
tokens_used:
  - tabs.segmented.secondary
  - padding.1
  - tabs.segmented.background
  - borderRadius.sm
  - padding.2
  - tabs.segmented.item.text
  - tabs.counter.background
  - radius
  - xs
  - tabs.counter.text
  - tabs.segmented.item.text_inactive
child_components:
  - tab-segmented-item
---

# TabsSegemented

> A horizontal tab bar with a segmented/pill style for switching between content panels.
AKA: Segmented Control, Segmented Tabs, Pill Tabs, Toggle Tabs, Tab Pills, Switcher

## Relationships

**Child components (used inside this component):**
- [`Tab Segmented Item`](./tab-segmented-item.component.md)

## Code contract

```typescript
interface TabsSegementedProps {
  /** Visual variant: Size */
  Size?: 'Regular' | 'Large' | 'Small';
  children?: React.ReactNode; // Accepts: Tab Segmented Item
  className?: string;
}
```

## Usage

```tsx
<TabsSegemented>
  <TabSegmentedItem />
  <TabSegmentedItem />
</TabsSegemented>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Size | `Regular`, `Large`, `Small` | `Regular` | Visual variant: Size |

## Anatomy

```
1. [Root] Size=Regular (COMPONENT)
  2. [Container] Tab Items (SLOT)
    3. [Container] 02 Tab Segmented Item (INSTANCE)
      4. [Label] Label (TEXT)
      5. [Container] .Tab Counter (INSTANCE)
        6. [Label] 1 (TEXT)
    7. [Container] 02 Tab Segmented Item (INSTANCE)
      8. [Label] Label (TEXT)
      9. [Container] .Tab Counter (INSTANCE)
        10. [Label] 1 (TEXT)
    11. [Container] 02 Tab Segmented Item (INSTANCE)
      12. [Label] Label (TEXT)
      13. [Container] .Tab Counter (INSTANCE)
        14. [Label] 1 (TEXT)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Size=Regular | fill | `#F5F5F5` | `tabs.segmented.secondary` | `var(--ach-tabs-segmented-secondary)` |
| Size=Regular | cornerRadius | `10px` | `—` | `—` |
| Size=Regular | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Size=Regular | paddingRight | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Size=Regular | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Size=Regular | paddingLeft | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Tab Segmented Item | fill | `#FFFFFF` | `tabs.segmented.background` | `var(--ach-tabs-segmented-background)` |
| 02 Tab Segmented Item | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 02 Tab Segmented Item | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Tab Segmented Item | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 Tab Segmented Item | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Tab Segmented Item | paddingLeft | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 Tab Segmented Item | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Label | fill | `#262626` | `tabs.segmented.item.text` | `var(--ach-tabs-segmented-item-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| .Tab Counter | fill | `#EEEEEE` | `tabs.counter.background` | `var(--ach-tabs-counter-background)` |
| .Tab Counter | cornerRadius | `10px` | `radius` | `var(--ach-radius)` |
| .Tab Counter | itemSpacing | `8px` | `xs` | `var(--ach-xs)` |
| 1 | fill | `#262626` | `tabs.counter.text` | `var(--ach-tabs-counter-text)` |
| 1 | fontSize | `10px` | `—` | `—` |
| 02 Tab Segmented Item | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 02 Tab Segmented Item | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Tab Segmented Item | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 Tab Segmented Item | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Tab Segmented Item | paddingLeft | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 Tab Segmented Item | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Label | fill | `#525252` | `tabs.segmented.item.text_inactive` | `var(--ach-tabs-segmented-item-text_inactive)` |
| Label | fontSize | `14px` | `—` | `—` |
| .Tab Counter | fill | `#EEEEEE` | `tabs.counter.background` | `var(--ach-tabs-counter-background)` |
| .Tab Counter | cornerRadius | `10px` | `radius` | `var(--ach-radius)` |
| .Tab Counter | itemSpacing | `8px` | `xs` | `var(--ach-xs)` |
| 1 | fill | `#262626` | `tabs.counter.text` | `var(--ach-tabs-counter-text)` |
| 1 | fontSize | `10px` | `—` | `—` |
| 02 Tab Segmented Item | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 02 Tab Segmented Item | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Tab Segmented Item | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 Tab Segmented Item | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Tab Segmented Item | paddingLeft | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 Tab Segmented Item | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Label | fill | `#525252` | `tabs.segmented.item.text_inactive` | `var(--ach-tabs-segmented-item-text_inactive)` |
| Label | fontSize | `14px` | `—` | `—` |
| .Tab Counter | fill | `#EEEEEE` | `tabs.counter.background` | `var(--ach-tabs-counter-background)` |
| .Tab Counter | cornerRadius | `10px` | `radius` | `var(--ach-radius)` |
| .Tab Counter | itemSpacing | `8px` | `xs` | `var(--ach-xs)` |
| 1 | fill | `#262626` | `tabs.counter.text` | `var(--ach-tabs-counter-text)` |
| 1 | fontSize | `10px` | `—` | `—` |

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
