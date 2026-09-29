---
id: breadcrumb-item
name: BreadcrumbItem
category: navigation
figma_component_name: "Breadcrumb item"
figma_url: "https://www.figma.com/design//?node-id=1096-2372"
status: draft
tokens_used:
  - padding.1
  - breadcrumb.text-default
  - breadcrumb.icon
parent_components:
  - breadcrumb
---

# BreadcrumbItem

> An individual link item within a Breadcrumb trail, representing a single navigation level.
AKA: Breadcrumb Link, Crumb, Path Item, Navigation Item

## Relationships

**Parent components (this component is used inside):**
- [`Breadcrumb`](./breadcrumb.component.md)

## Code contract

```typescript
interface BreadcrumbItemProps {
  /** Text content: ⮑ Label */
  ⮑ Label?: React.ReactNode;
  /** Toggle: Dropdown menu */
  Dropdown menu?: boolean;
  /** Slot: Icon */
  Icon?: React.ReactNode;
  /** Visual variant: State */
  State?: 'Default' | 'Hover' | 'Active';
  /** Visual variant: Label */
  Label?: 'Label' | 'Icon';
  children?: React.ReactNode;
  className?: string;
}
```

## Usage

> This component is designed to be used inside [`Breadcrumb`](./breadcrumb.component.md).

```tsx
<Breadcrumb>
  <BreadcrumbItem />
  <BreadcrumbItem />
</Breadcrumb>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| State | `Default`, `Hover`, `Active` | `Default` | Visual variant: State |
| Label | `Label`, `Icon` | `Label` | Visual variant: Label |

## Anatomy

```
1. [Root] State=Default, Label=Label (COMPONENT)
  2. [Label] Label (TEXT)
  3. [Icon] Icons/ui-actions/expand-more (INSTANCE)
    4. [Element] Vector (VECTOR)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| State=Default, Label=Label | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Label | fill | `#737373` | `breadcrumb.text-default` | `var(--ach-breadcrumb-text-default)` |
| Label | fontSize | `14px` | `—` | `—` |
| Icons/ui-actions/expand-more | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `breadcrumb.icon` | `var(--ach-breadcrumb-icon)` |

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


---

---
id: breadcrumb
name: Breadcrumb
category: navigation
figma_component_name: "Breadcrumb"
figma_url: "https://www.figma.com/design//?node-id=1096-2884"
status: draft
tokens_used:
  - padding.1
  - breadcrumb.text-default
  - breadcrumb.icon
  - breadcrumb.text-active
child_components:
  - breadcrumb-item
---

# Breadcrumb

> A horizontal navigation trail showing the user's current location within a site or app hierarchy.
AKA: Breadcrumb Trail, Navigation Path, Page Path, Crumb Trail, Location Trail

## Relationships

**Child components (used inside this component):**
- [`Breadcrumb item`](./breadcrumb-item.component.md)

## Code contract

```typescript
interface BreadcrumbProps {
  /** Visual variant: Levels */
  Levels?: '2' | '3' | '4' | '5' | '6';
  children?: React.ReactNode; // Accepts: Breadcrumb item
  className?: string;
}
```

## Usage

```tsx
<Breadcrumb>
  <BreadcrumbItem />
  <BreadcrumbItem />
</Breadcrumb>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Levels | `2`, `3`, `4`, `5`, `6` | `2` | Visual variant: Levels |

## Anatomy

```
1. [Root] Levels=2 (COMPONENT)
  2. [Container] Content (SLOT)
    3. [Container] 02 Breadcrumb item (INSTANCE)
      4. [Label] Label (TEXT)
      5. [Icon] Icons/ui-actions/expand-more (INSTANCE)
        6. [Element] Vector (VECTOR)
    7. [Icon] Icons/ui-actions/chevron-right (INSTANCE)
      8. [Element] Vector (VECTOR)
    9. [Container] 02 Breadcrumb item (INSTANCE)
      10. [Label] Label (TEXT)
      11. [Icon] Icons/ui-actions/expand-more (INSTANCE)
        12. [Element] Vector (VECTOR)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Levels=2 | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Content | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Breadcrumb item | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Label | fill | `#737373` | `breadcrumb.text-default` | `var(--ach-breadcrumb-text-default)` |
| Label | fontSize | `14px` | `—` | `—` |
| Icons/ui-actions/expand-more | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `breadcrumb.icon` | `var(--ach-breadcrumb-icon)` |
| Icons/ui-actions/chevron-right | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `breadcrumb.icon` | `var(--ach-breadcrumb-icon)` |
| 02 Breadcrumb item | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Label | fill | `#262626` | `breadcrumb.text-active` | `var(--ach-breadcrumb-text-active)` |
| Label | fontSize | `14px` | `—` | `—` |
| Icons/ui-actions/expand-more | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `breadcrumb.icon` | `var(--ach-breadcrumb-icon)` |

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
