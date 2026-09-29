---
id: timeline-item
name: TimelineItem
category: primitive
figma_component_name: "Timeline Item"
figma_url: "https://www.figma.com/design//?node-id=1302-85"
status: draft
tokens_used:
  - padding.3
  - timeline.line
  - timeline.default.icon
  - padding.1
  - padding.6
  - timeline.default.title
  - timeline.text_secondary
  - timeline.text_tertiary
parent_components:
  - timeline
---

# TimelineItem

> An individual event or step within a Timeline, with status icon, connector line, and content.
AKA: Timeline Entry, Timeline Event, Timeline Step, Activity Item, History Item

## Relationships

**Parent components (this component is used inside):**
- [`Timeline`](./timeline.component.md)

## Code contract

```typescript
interface TimelineItemProps {
  /** Text content: Title */
  Title?: React.ReactNode;
  /** Text content: Description */
  Description?: React.ReactNode;
  /** Text content: Timestamp */
  Timestamp?: React.ReactNode;
  /** Toggle: Show Top Line */
  Show Top Line?: boolean;
  /** Toggle: Show Bottom Line */
  Show Bottom Line?: boolean;
  /** Visual variant: Status */
  Status?: 'Active' | 'Default' | 'Success' | 'Error' | 'Warning' | 'Info' | 'Disabled';
  /** Visual variant: Orientation */
  Orientation?: 'Vertical' | 'Horizontal';
  children?: React.ReactNode;
  className?: string;
}
```

## Usage

> This component is designed to be used inside [`Timeline`](./timeline.component.md).

```tsx
<Timeline>
  <TimelineItem />
  <TimelineItem />
</Timeline>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Status | `Active`, `Default`, `Success`, `Error`, `Warning`, `Info`, `Disabled` | `Default` | Visual variant: Status |
| Orientation | `Vertical`, `Horizontal` | `Vertical` | Visual variant: Orientation |

## Anatomy

```
1. [Root] Status=Default, Orientation=Vertical (COMPONENT)
  2. [Container] Indicator (FRAME)
    3. [Element] Line Top (FRAME)
    4. [Icon] Icon (ELLIPSE)
    5. [Element] Line Bottom (FRAME)
  6. [Container] Content (FRAME)
    7. [Label] Title (TEXT)
    8. [Label] Description (TEXT)
    9. [Label] Timestamp (TEXT)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Status=Default, Orientation=Vertical | itemSpacing | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Line Top | fill | `#DCDCDC` | `timeline.line` | `var(--ach-timeline-line)` |
| Icon | stroke | `#DCDCDC` | `timeline.default.icon` | `var(--ach-timeline-default-icon)` |
| Line Bottom | fill | `#DCDCDC` | `timeline.line` | `var(--ach-timeline-line)` |
| Content | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Content | paddingBottom | `24px` | `padding.6` | `var(--ach-padding-6)` |
| Content | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Title | fill | `#262626` | `timeline.default.title` | `var(--ach-timeline-default-title)` |
| Title | fontSize | `14px` | `—` | `—` |
| Description | fill | `#525252` | `timeline.text_secondary` | `var(--ach-timeline-text_secondary)` |
| Description | fontSize | `12px` | `—` | `—` |
| Timestamp | fill | `#737373` | `timeline.text_tertiary` | `var(--ach-timeline-text_tertiary)` |
| Timestamp | fontSize | `12px` | `—` | `—` |

## States

| State | Present | Notes |
| :--- | :--- | :--- |
| Default | ✅ | Defined in Figma |
| Hover | ❌ | Not found — add variant or document manually |
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
id: timeline
name: Timeline
category: primitive
figma_component_name: "Timeline"
figma_url: "https://www.figma.com/design//?node-id=1302-86"
status: draft
tokens_used:
  - padding.3
  - timeline.line
  - timeline.default.icon
  - padding.1
  - padding.6
  - timeline.default.title
  - timeline.text_secondary
  - timeline.text_tertiary
  - timeline.active.icon
  - timeline.active.title
  - timeline.success.icon
  - timeline.success.title
child_components:
  - timeline-item
---

# Timeline

> A vertical sequence of events or steps displayed in chronological order.
AKA: Activity Feed, Event Timeline, History, Stepper, Activity Log, Time Feed

## Relationships

**Child components (used inside this component):**
- [`Timeline Item`](./timeline-item.component.md)

## Code contract

```typescript
interface TimelineProps {
  children?: React.ReactNode; // Accepts: Timeline Item
  className?: string;
}
```

## Usage

```tsx
<Timeline>
  <TimelineItem />
  <TimelineItem />
</Timeline>
```

## Anatomy

```
1. [Root] 01 Timeline (COMPONENT)
  2. [Container] Timeline Slot (SLOT)
    3. [Container] 02 Timeline Item (INSTANCE)
      4. [Container] Indicator (FRAME)
        5. [Element] Line Top (FRAME)
        6. [Icon] Icon (ELLIPSE)
        7. [Element] Line Bottom (FRAME)
      8. [Container] Content (FRAME)
        9. [Label] Title (TEXT)
        10. [Label] Description (TEXT)
        11. [Label] Timestamp (TEXT)
    12. [Container] 02 Timeline Item (INSTANCE)
      13. [Container] Indicator (FRAME)
        14. [Element] Line Top (FRAME)
        15. [Icon] Icon (FRAME)
          16. [Element] Ellipse (ELLIPSE)
          17. [Element] Ellipse (ELLIPSE)
        18. [Element] Line Bottom (FRAME)
      19. [Container] Content (FRAME)
        20. [Label] Title (TEXT)
        21. [Label] Description (TEXT)
        22. [Label] Timestamp (TEXT)
    23. [Container] 02 Timeline Item (INSTANCE)
      24. [Container] Indicator (FRAME)
        25. [Element] Line Top (FRAME)
        26. [Icon] Icon (INSTANCE)
          27. [Element] Vector (VECTOR)
        28. [Element] Line Bottom (FRAME)
      29. [Container] Content (FRAME)
        30. [Label] Title (TEXT)
        31. [Label] Description (TEXT)
        32. [Label] Timestamp (TEXT)
    33. [Container] 02 Timeline Item (INSTANCE)
      34. [Container] Indicator (FRAME)
        35. [Element] Line Top (FRAME)
        36. [Icon] Icon (INSTANCE)
          37. [Element] Vector (VECTOR)
        38. [Element] Line Bottom (FRAME)
      39. [Container] Content (FRAME)
        40. [Label] Title (TEXT)
        41. [Label] Description (TEXT)
        42. [Label] Timestamp (TEXT)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| 02 Timeline Item | itemSpacing | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Line Top | fill | `#DCDCDC` | `timeline.line` | `var(--ach-timeline-line)` |
| Icon | stroke | `#DCDCDC` | `timeline.default.icon` | `var(--ach-timeline-default-icon)` |
| Line Bottom | fill | `#DCDCDC` | `timeline.line` | `var(--ach-timeline-line)` |
| Content | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Content | paddingBottom | `24px` | `padding.6` | `var(--ach-padding-6)` |
| Content | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Title | fill | `#262626` | `timeline.default.title` | `var(--ach-timeline-default-title)` |
| Title | fontSize | `14px` | `—` | `—` |
| Description | fill | `#525252` | `timeline.text_secondary` | `var(--ach-timeline-text_secondary)` |
| Description | fontSize | `12px` | `—` | `—` |
| Timestamp | fill | `#737373` | `timeline.text_tertiary` | `var(--ach-timeline-text_tertiary)` |
| Timestamp | fontSize | `12px` | `—` | `—` |
| 02 Timeline Item | itemSpacing | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Line Top | fill | `#DCDCDC` | `timeline.line` | `var(--ach-timeline-line)` |
| Ellipse | fill | `#005CFF` | `timeline.active.icon` | `var(--ach-timeline-active-icon)` |
| Ellipse | fill | `#005CFF` | `timeline.active.icon` | `var(--ach-timeline-active-icon)` |
| Line Bottom | fill | `#DCDCDC` | `timeline.line` | `var(--ach-timeline-line)` |
| Content | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Content | paddingBottom | `24px` | `padding.6` | `var(--ach-padding-6)` |
| Content | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Title | fill | `#262626` | `timeline.active.title` | `var(--ach-timeline-active-title)` |
| Title | fontSize | `14px` | `—` | `—` |
| Description | fill | `#525252` | `timeline.text_secondary` | `var(--ach-timeline-text_secondary)` |
| Description | fontSize | `12px` | `—` | `—` |
| Timestamp | fill | `#737373` | `timeline.text_tertiary` | `var(--ach-timeline-text_tertiary)` |
| Timestamp | fontSize | `12px` | `—` | `—` |
| 02 Timeline Item | itemSpacing | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Line Top | fill | `#DCDCDC` | `timeline.line` | `var(--ach-timeline-line)` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#16A34A` | `timeline.success.icon` | `var(--ach-timeline-success-icon)` |
| Line Bottom | fill | `#DCDCDC` | `timeline.line` | `var(--ach-timeline-line)` |
| Content | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Content | paddingBottom | `24px` | `padding.6` | `var(--ach-padding-6)` |
| Content | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Title | fill | `#15803D` | `timeline.success.title` | `var(--ach-timeline-success-title)` |
| Title | fontSize | `14px` | `—` | `—` |
| Description | fill | `#525252` | `timeline.text_secondary` | `var(--ach-timeline-text_secondary)` |
| Description | fontSize | `12px` | `—` | `—` |
| Timestamp | fill | `#737373` | `timeline.text_tertiary` | `var(--ach-timeline-text_tertiary)` |
| Timestamp | fontSize | `12px` | `—` | `—` |
| 02 Timeline Item | itemSpacing | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Line Top | fill | `#DCDCDC` | `timeline.line` | `var(--ach-timeline-line)` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#16A34A` | `timeline.success.icon` | `var(--ach-timeline-success-icon)` |
| Line Bottom | fill | `#DCDCDC` | `timeline.line` | `var(--ach-timeline-line)` |
| Content | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Content | paddingBottom | `24px` | `padding.6` | `var(--ach-padding-6)` |
| Content | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Title | fill | `#15803D` | `timeline.success.title` | `var(--ach-timeline-success-title)` |
| Title | fontSize | `14px` | `—` | `—` |
| Description | fill | `#525252` | `timeline.text_secondary` | `var(--ach-timeline-text_secondary)` |
| Description | fontSize | `12px` | `—` | `—` |
| Timestamp | fill | `#737373` | `timeline.text_tertiary` | `var(--ach-timeline-text_tertiary)` |
| Timestamp | fontSize | `12px` | `—` | `—` |

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
