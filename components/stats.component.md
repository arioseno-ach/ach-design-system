---
id: stats-item
name: StatsItem
category: primitive
figma_component_name: "Stats Item"
figma_url: "https://www.figma.com/design//?node-id=1384-57635"
status: draft
tokens_used:
  - stats.item.background
  - padding.4
  - padding.5
  - stats.item.number
  - padding.1
  - padding.2
  - stats.item.title
  - stats.item.subtitle
  - divider.default
parent_components:
  - stats
---

# StatsItem

> An individual metric display within a Stats group, showing a label, value, and optional trend.
AKA: Stat Card, Metric Item, KPI Item, Data Point, Stat Tile

## Relationships

**Parent components (this component is used inside):**
- [`Stats`](./stats.component.md)

## Code contract

```typescript
interface StatsItemProps {
  /** Text content: Number */
  Number?: React.ReactNode;
  /** Text content: Title */
  Title?: React.ReactNode;
  /** Text content: Subtitle */
  Subtitle?: React.ReactNode;
  /** Toggle: Show Subtitle */
  Show Subtitle?: boolean;
  /** Visual variant: State */
  State?: 'Default' | 'Hover';
  /** Visual variant: Border Right */
  Border Right?: 'True' | 'False';
  children?: React.ReactNode;
  className?: string;
}
```

## Usage

> This component is designed to be used inside [`Stats`](./stats.component.md).

```tsx
<Stats>
  <StatsItem />
  <StatsItem />
</Stats>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| State | `Default`, `Hover` | `Default` | Visual variant: State |
| Border Right | `True`, `False` | `False` | Visual variant: Border Right |

## Anatomy

```
1. [Root] State=Default, Border Right=False (COMPONENT)
  2. [Container] Content (FRAME)
    3. [Container] Number (FRAME)
      4. [Label] Number (TEXT)
    5. [Container] Div (FRAME)
      6. [Container] Title (FRAME)
        7. [Label] Title (TEXT)
      8. [Container] Subtitle (FRAME)
        9. [Label] Subtitle (TEXT)
  10. [Divider] 01 Divider (INSTANCE)
    11. [Divider] Divider (RECTANGLE)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| State=Default, Border Right=False | fill | `#FFFFFF` | `stats.item.background` | `var(--ach-stats-item-background)` |
| Content | paddingTop | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Content | paddingRight | `20px` | `padding.5` | `var(--ach-padding-5)` |
| Content | paddingBottom | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Content | paddingLeft | `20px` | `padding.5` | `var(--ach-padding-5)` |
| Number | fill | `#262626` | `stats.item.number` | `var(--ach-stats-item-number)` |
| Number | fontSize | `20px` | `—` | `—` |
| Div | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Title | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Title | fill | `#525252` | `stats.item.title` | `var(--ach-stats-item-title)` |
| Title | fontSize | `10px` | `—` | `—` |
| Subtitle | fill | `#737373` | `stats.item.subtitle` | `var(--ach-stats-item-subtitle)` |
| Subtitle | fontSize | `10px` | `—` | `—` |
| Divider | fill | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |

## States

| State | Present | Notes |
| :--- | :--- | :--- |
| Default | ✅ | Defined in Figma |
| Hover | ✅ | Defined in Figma |
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
id: stats
name: Stats
category: primitive
figma_component_name: "Stats"
figma_url: "https://www.figma.com/design//?node-id=1384-57668"
status: draft
tokens_used:
  - stats.border
  - borderRadius.lg
  - stats.item.background
  - padding.4
  - padding.5
  - stats.item.number
  - padding.1
  - padding.2
  - stats.item.title
  - stats.item.subtitle
  - divider.default
child_components:
  - stats-item
---

# Stats

> A container displaying a group of key metrics or statistics in a structured layout.
AKA: Metrics, KPI Card, Stat Group, Data Summary, Key Figures, Stats Overview

## Relationships

**Child components (used inside this component):**
- [`Stats Item`](./stats-item.component.md)

## Code contract

```typescript
interface StatsProps {
  /** Visual variant: Count */
  Count?: '2' | '3' | '4' | '5' | '6';
  children?: React.ReactNode; // Accepts: Stats Item
  className?: string;
}
```

## Usage

```tsx
<Stats>
  <StatsItem />
  <StatsItem />
</Stats>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Count | `2`, `3`, `4`, `5`, `6` | `2` | Visual variant: Count |

## Anatomy

```
1. [Root] Count=2 (COMPONENT)
  2. [Container] Container (SLOT)
    3. [Container] 02 Stats Item (INSTANCE)
      4. [Container] Content (FRAME)
        5. [Container] Number (FRAME)
          6. [Label] Number (TEXT)
        7. [Container] Div (FRAME)
          8. [Container] Title (FRAME)
            9. [Label] Title (TEXT)
          10. [Container] Subtitle (FRAME)
            11. [Label] Subtitle (TEXT)
      12. [Divider] 01 Divider (INSTANCE)
        13. [Divider] Divider (RECTANGLE)
    14. [Container] 02 Stats Item (INSTANCE)
      15. [Container] Content (FRAME)
        16. [Container] Number (FRAME)
          17. [Label] Number (TEXT)
        18. [Container] Div (FRAME)
          19. [Container] Title (FRAME)
            20. [Label] Title (TEXT)
          21. [Container] Subtitle (FRAME)
            22. [Label] Subtitle (TEXT)
      23. [Divider] 01 Divider (INSTANCE)
        24. [Divider] Divider (RECTANGLE)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Count=2 | stroke | `#DCDCDC` | `stats.border` | `var(--ach-stats-border)` |
| Count=2 | cornerRadius | `16px` | `borderRadius.lg` | `var(--ach-borderRadius-lg)` |
| 02 Stats Item | fill | `#FFFFFF` | `stats.item.background` | `var(--ach-stats-item-background)` |
| Content | paddingTop | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Content | paddingRight | `20px` | `padding.5` | `var(--ach-padding-5)` |
| Content | paddingBottom | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Content | paddingLeft | `20px` | `padding.5` | `var(--ach-padding-5)` |
| Number | fill | `#262626` | `stats.item.number` | `var(--ach-stats-item-number)` |
| Number | fontSize | `20px` | `—` | `—` |
| Div | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Title | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Title | fill | `#525252` | `stats.item.title` | `var(--ach-stats-item-title)` |
| Title | fontSize | `10px` | `—` | `—` |
| Subtitle | fill | `#737373` | `stats.item.subtitle` | `var(--ach-stats-item-subtitle)` |
| Subtitle | fontSize | `10px` | `—` | `—` |
| Divider | fill | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Stats Item | fill | `#FFFFFF` | `stats.item.background` | `var(--ach-stats-item-background)` |
| Content | paddingTop | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Content | paddingRight | `20px` | `padding.5` | `var(--ach-padding-5)` |
| Content | paddingBottom | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Content | paddingLeft | `20px` | `padding.5` | `var(--ach-padding-5)` |
| Number | fill | `#262626` | `stats.item.number` | `var(--ach-stats-item-number)` |
| Number | fontSize | `20px` | `—` | `—` |
| Div | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Title | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Title | fill | `#525252` | `stats.item.title` | `var(--ach-stats-item-title)` |
| Title | fontSize | `10px` | `—` | `—` |
| Subtitle | fill | `#737373` | `stats.item.subtitle` | `var(--ach-stats-item-subtitle)` |
| Subtitle | fontSize | `10px` | `—` | `—` |
| Divider | fill | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |

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
