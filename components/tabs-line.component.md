---
id: tab-line-item
name: TabLineItem
category: navigation
figma_component_name: "Tab Line Item"
figma_url: "https://www.figma.com/design//?node-id=1563-975"
status: draft
tokens_used:
  - padding.1
  - padding.2
  - tabs.line.item.text_inactive
  - tabs.counter.background
  - borderRadius.sm
  - tabs.counter.text
parent_components:
  - tabs-line
---

# TabLineItem

> An individual tab within a Line Tab bar, with active indicator and label.
AKA: Tab, Tab Button, Tab Item, Navigation Tab, Tab Link

## Relationships

**Parent components (this component is used inside):**
- [`Tabs Line`](./tabs-line.component.md)

## Code contract

```typescript
interface TabLineItemProps {
  /** Text content: Tab Label */
  Tab Label?: React.ReactNode;
  /** Toggle: Show counter */
  Show counter?: boolean;
  /** Slot: Icon */
  Icon?: React.ReactNode;
  /** Visual variant: Size */
  Size?: 'Regular' | 'Small';
  /** Visual variant: Content */
  Content?: 'Label' | 'Icon' | 'Icon + Label';
  /** Visual variant: State */
  State?: 'Inactive' | 'Inactive Hover' | 'Inactive Focus' | 'Active' | 'Active Focus' | 'Disabled';
  children?: React.ReactNode;
  className?: string;
}
```

## Usage

> This component is designed to be used inside [`Tabs Line`](./tabs-line.component.md).

```tsx
<TabsLine>
  <TabLineItem />
  <TabLineItem />
</TabsLine>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Size | `Regular`, `Small` | `Regular` | Visual variant: Size |
| Content | `Label`, `Icon`, `Icon + Label` | `Label` | Visual variant: Content |
| State | `Inactive`, `Inactive Hover`, `Inactive Focus`, `Active`, `Active Focus`, `Disabled` | `Inactive` | Visual variant: State |

## Anatomy

```
1. [Root] Size=Regular, Content=Label, State=Inactive (COMPONENT)
  2. [Container] Content (FRAME)
    3. [Label] Label (TEXT)
    4. [Container] .Tab Counter (INSTANCE)
      5. [Label] 1 (TEXT)
  6. [Element] Indicator (RECTANGLE)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Content | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Content | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Content | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Content | paddingLeft | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Content | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Label | fill | `#525252` | `tabs.line.item.text_inactive` | `var(--ach-tabs-line-item-text_inactive)` |
| Label | fontSize | `14px` | `—` | `—` |
| .Tab Counter | fill | `#EEEEEE` | `tabs.counter.background` | `var(--ach-tabs-counter-background)` |
| .Tab Counter | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 1 | fill | `#262626` | `tabs.counter.text` | `var(--ach-tabs-counter-text)` |
| 1 | fontSize | `10px` | `—` | `—` |

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
id: tabs-line
name: TabsLine
category: navigation
figma_component_name: "Tabs Line"
figma_url: "https://www.figma.com/design//?node-id=1563-39122"
status: draft
tokens_used:
  - tabs.line.border
  - padding.1
  - padding.2
  - tabs.line.item.text_active
  - tabs.counter.background
  - borderRadius.sm
  - tabs.counter.text
  - tabs.line.item.indicator
  - tabs.line.item.text_inactive
child_components:
  - tab-line-item
---

# TabsLine

> A horizontal tab bar with an underline indicator for switching between content panels.
AKA: Tab Bar, Underline Tabs, Navigation Tabs, Content Tabs, Tab Navigation

## Relationships

**Child components (used inside this component):**
- [`Tab Line Item`](./tab-line-item.component.md)

## Code contract

```typescript
interface TabsLineProps {
  /** Visual variant: Size */
  Size?: 'Regular' | 'Small';
  children?: React.ReactNode; // Accepts: Tab Line Item
  className?: string;
}
```

## Usage

```tsx
<TabsLine>
  <TabLineItem />
  <TabLineItem />
</TabsLine>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Size | `Regular`, `Small` | `Regular` | Visual variant: Size |

## Anatomy

```
1. [Root] Size=Regular (COMPONENT)
  2. [Container] Tab Items (SLOT)
    3. [Container] Tab Items (INSTANCE)
      4. [Container] Content (FRAME)
        5. [Label] Label (TEXT)
        6. [Container] .Tab Counter (INSTANCE)
          7. [Label] 1 (TEXT)
      8. [Element] Indicator (RECTANGLE)
    9. [Container] Tab Items (INSTANCE)
      10. [Container] Content (FRAME)
        11. [Label] Label (TEXT)
        12. [Container] .Tab Counter (INSTANCE)
          13. [Label] 1 (TEXT)
      14. [Element] Indicator (RECTANGLE)
    15. [Container] Tab Items (INSTANCE)
      16. [Container] Content (FRAME)
        17. [Label] Label (TEXT)
        18. [Container] .Tab Counter (INSTANCE)
          19. [Label] 1 (TEXT)
      20. [Element] Indicator (RECTANGLE)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Size=Regular | stroke | `#EEEEEE` | `tabs.line.border` | `var(--ach-tabs-line-border)` |
| Content | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Content | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Content | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Content | paddingLeft | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Content | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Label | fill | `#262626` | `tabs.line.item.text_active` | `var(--ach-tabs-line-item-text_active)` |
| Label | fontSize | `14px` | `—` | `—` |
| .Tab Counter | fill | `#EEEEEE` | `tabs.counter.background` | `var(--ach-tabs-counter-background)` |
| .Tab Counter | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 1 | fill | `#262626` | `tabs.counter.text` | `var(--ach-tabs-counter-text)` |
| 1 | fontSize | `10px` | `—` | `—` |
| Indicator | fill | `#171717` | `tabs.line.item.indicator` | `var(--ach-tabs-line-item-indicator)` |
| Content | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Content | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Content | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Content | paddingLeft | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Content | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Label | fill | `#525252` | `tabs.line.item.text_inactive` | `var(--ach-tabs-line-item-text_inactive)` |
| Label | fontSize | `14px` | `—` | `—` |
| .Tab Counter | fill | `#EEEEEE` | `tabs.counter.background` | `var(--ach-tabs-counter-background)` |
| .Tab Counter | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| 1 | fill | `#262626` | `tabs.counter.text` | `var(--ach-tabs-counter-text)` |
| 1 | fontSize | `10px` | `—` | `—` |
| Content | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Content | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Content | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Content | paddingLeft | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Content | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Label | fill | `#525252` | `tabs.line.item.text_inactive` | `var(--ach-tabs-line-item-text_inactive)` |
| Label | fontSize | `14px` | `—` | `—` |
| .Tab Counter | fill | `#EEEEEE` | `tabs.counter.background` | `var(--ach-tabs-counter-background)` |
| .Tab Counter | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
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
