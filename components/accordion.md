---
id: accordion-item
name: AccordionItem
category: primitive
figma_component_name: "Accordion Item"
figma_url: "https://www.figma.com/design//?node-id=1213-15818"
status: draft
tokens_used:
  - accordion.background
  - padding.4
  - padding.3
  - accordion.title
  - accordion.icon
  - accordion.border
parent_components:
  - accordion
---

# AccordionItem

> An individual item within an Accordion. Contains a header trigger and expandable content area.
AKA: Accordion Section, Expandable Item, Collapse Item, Disclosure Item

## Relationships

**Parent components (this component is used inside):**
- [`Accordion`](./accordion.component.md)

## Code contract

```typescript
interface AccordionItemProps {
  /** Text content: Title */
  Title?: React.ReactNode;
  /** Text content: Content */
  Content?: React.ReactNode;
  /** Visual variant: isExpanded */
  isExpanded?: 'false' | 'true';
  /** Visual variant: isDisabled */
  isDisabled?: 'false' | 'true';
  children?: React.ReactNode;
  className?: string;
}
```

## Usage

> This component is designed to be used inside [`Accordion`](./accordion.component.md).

```tsx
<Accordion>
  <AccordionItem />
  <AccordionItem />
</Accordion>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| isExpanded | `false`, `true` | `false` | Visual variant: isExpanded |
| isDisabled | `false`, `true` | `false` | Visual variant: isDisabled |

## Anatomy

```
1. [Root] isExpanded=false, isDisabled=false (COMPONENT)
  2. [Container] Header (FRAME)
    3. [Label] Title (TEXT)
    4. [Icon] Icon (INSTANCE)
      5. [Element] Vector (VECTOR)
  6. [Divider] 01 Divider (INSTANCE)
    7. [Divider] Divider (RECTANGLE)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| isExpanded=false, isDisabled=false | fill | `#FFFFFF` | `accordion.background` | `var(--ach-accordion-background)` |
| Header | paddingTop | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Header | paddingBottom | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Header | itemSpacing | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Title | fill | `#262626` | `accordion.title` | `var(--ach-accordion-title)` |
| Title | fontSize | `14px` | `—` | `—` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `accordion.icon` | `var(--ach-accordion-icon)` |
| Divider | stroke | `#DCDCDC` | `accordion.border` | `var(--ach-accordion-border)` |

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
id: accordion
name: Accordion
category: primitive
figma_component_name: "Accordion"
figma_url: "https://www.figma.com/design//?node-id=1239-35"
status: draft
tokens_used:
  - accordion.background
  - padding.4
  - padding.3
  - accordion.title
  - accordion.icon
  - accordion.border
child_components:
  - accordion-item
---

# Accordion

> A collapsible content container that expands and collapses to show or hide sections of content.
AKA: Expandable, Collapsible, Disclosure, Expand/Collapse Panel, FAQ

## Relationships

**Child components (used inside this component):**
- [`Accordion Item`](./accordion-item.component.md)

## Code contract

```typescript
interface AccordionProps {
  children?: React.ReactNode; // Accepts: Accordion Item
  className?: string;
}
```

## Usage

```tsx
<Accordion>
  <AccordionItem />
  <AccordionItem />
</Accordion>
```

## Anatomy

```
1. [Root] 01 Accordion (COMPONENT)
  2. [Container] Slot Accordion (SLOT)
    3. [Container] 02 Accordion Item (INSTANCE)
      4. [Container] Header (FRAME)
        5. [Label] Title (TEXT)
        6. [Icon] Icon (INSTANCE)
          7. [Element] Vector (VECTOR)
      8. [Divider] 01 Divider (INSTANCE)
        9. [Divider] Divider (RECTANGLE)
    10. [Container] 02 Accordion Item (INSTANCE)
      11. [Container] Header (FRAME)
        12. [Label] Title (TEXT)
        13. [Icon] Icon (INSTANCE)
          14. [Element] Vector (VECTOR)
      15. [Divider] 01 Divider (INSTANCE)
        16. [Divider] Divider (RECTANGLE)
    17. [Container] 02 Accordion Item (INSTANCE)
      18. [Container] Header (FRAME)
        19. [Label] Title (TEXT)
        20. [Icon] Icon (INSTANCE)
          21. [Element] Vector (VECTOR)
      22. [Divider] 01 Divider (INSTANCE)
        23. [Divider] Divider (RECTANGLE)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| 02 Accordion Item | fill | `#FFFFFF` | `accordion.background` | `var(--ach-accordion-background)` |
| Header | paddingTop | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Header | paddingBottom | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Header | itemSpacing | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Title | fill | `#262626` | `accordion.title` | `var(--ach-accordion-title)` |
| Title | fontSize | `14px` | `—` | `—` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `accordion.icon` | `var(--ach-accordion-icon)` |
| Divider | stroke | `#DCDCDC` | `accordion.border` | `var(--ach-accordion-border)` |
| 02 Accordion Item | fill | `#FFFFFF` | `accordion.background` | `var(--ach-accordion-background)` |
| Header | paddingTop | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Header | paddingBottom | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Header | itemSpacing | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Title | fill | `#262626` | `accordion.title` | `var(--ach-accordion-title)` |
| Title | fontSize | `14px` | `—` | `—` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `accordion.icon` | `var(--ach-accordion-icon)` |
| Divider | stroke | `#DCDCDC` | `accordion.border` | `var(--ach-accordion-border)` |
| 02 Accordion Item | fill | `#FFFFFF` | `accordion.background` | `var(--ach-accordion-background)` |
| Header | paddingTop | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Header | paddingBottom | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Header | itemSpacing | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Title | fill | `#262626` | `accordion.title` | `var(--ach-accordion-title)` |
| Title | fontSize | `14px` | `—` | `—` |
| Icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `accordion.icon` | `var(--ach-accordion-icon)` |
| Divider | stroke | `#DCDCDC` | `accordion.border` | `var(--ach-accordion-border)` |

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
