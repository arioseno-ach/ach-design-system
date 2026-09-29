---
id: .pagination-navigation
name: .PaginationNavigation
category: navigation
figma_component_name: ".Pagination Navigation"
figma_url: "https://www.figma.com/design//?node-id=1354-26684"
status: draft
tokens_used:
  - borderRadius.xs
  - padding.1
  - pagination.nav.icon
parent_components:
  - .pagination-navigation-group
  - pagination
---

# .PaginationNavigation

> An individual pagination navigation button (first, previous, next, last page).
AKA: Page Arrow, Nav Arrow, Pagination Button, Page Control Button

## Relationships

**Parent components (this component is used inside):**
- [`.Pagination Navigation Group`](./.pagination-navigation-group.component.md)
- [`Pagination`](./pagination.component.md)

## Code contract

```typescript
interface .PaginationNavigationProps {
  /** Visual variant: Property 1 */
  Property 1?: 'First' | 'Last' | 'Next' | 'Previous';
  children?: React.ReactNode;
  className?: string;
}
```

## Usage

> This component is designed to be used inside [`.Pagination Navigation Group`](./.pagination-navigation-group.component.md).

```tsx
<.PaginationNavigationGroup>
  <.PaginationNavigation />
  <.PaginationNavigation />
</.PaginationNavigationGroup>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Property 1 | `First`, `Last`, `Next`, `Previous` | `First` | Visual variant: Property 1 |

## Anatomy

```
1. [Root] Property 1=First (COMPONENT)
  2. [Icon] Icons/ui-actions/first-page (INSTANCE)
    3. [Element] Vector (VECTOR)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Property 1=First | cornerRadius | `4px` | `borderRadius.xs` | `var(--ach-borderRadius-xs)` |
| Property 1=First | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Property 1=First | paddingRight | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Property 1=First | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Property 1=First | paddingLeft | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Icons/ui-actions/first-page | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `pagination.nav.icon` | `var(--ach-pagination-nav-icon)` |

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
id: .pagination-information
name: .PaginationInformation
category: navigation
figma_component_name: ".Pagination Information"
figma_url: "https://www.figma.com/design//?node-id=1354-26685"
status: draft
tokens_used:
  - pagination.label.text
parent_components:
  - .pagination-navigation-group
  - pagination
---

# .PaginationInformation

> A text label within pagination displaying contextual info like page count, record count, or rows per page.
AKA: Page Info, Pagination Label, Page Counter, Record Info, Rows Per Page

## Relationships

**Parent components (this component is used inside):**
- [`.Pagination Navigation Group`](./.pagination-navigation-group.component.md)
- [`Pagination`](./pagination.component.md)

## Code contract

```typescript
interface .PaginationInformationProps {
  /** Text content: Value */
  Value?: React.ReactNode;
  /** Text content: Label */
  Label?: React.ReactNode;
  /** Visual variant: Property 1 */
  Property 1?: 'Page Info' | 'Record Info' | 'Rows Per Page';
  children?: React.ReactNode;
  className?: string;
}
```

## Usage

> This component is designed to be used inside [`.Pagination Navigation Group`](./.pagination-navigation-group.component.md).

```tsx
<.PaginationNavigationGroup>
  <.PaginationInformation />
  <.PaginationInformation />
</.PaginationNavigationGroup>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Property 1 | `Page Info`, `Record Info`, `Rows Per Page` | `Record Info` | Visual variant: Property 1 |

## Anatomy

```
1. [Root] Property 1=Record Info (COMPONENT)
  2. [Label] 1 of 3 (TEXT)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| 1 of 3 | fill | `#525252` | `pagination.label.text` | `var(--ach-pagination-label-text)` |
| 1 of 3 | fontSize | `12px` | `—` | `—` |

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
id: .pagination-navigation-group
name: .PaginationNavigationGroup
category: navigation
figma_component_name: ".Pagination Navigation Group"
figma_url: "https://www.figma.com/design//?node-id=1365-205"
status: draft
tokens_used:
  - padding.1
  - borderRadius.xs
  - pagination.nav.icon_disabled
  - pagination.label.text
  - pagination.nav.icon
child_components:
  - .pagination-navigation
  - .pagination-information
parent_components:
  - pagination
---

# .PaginationNavigationGroup

> A group container for pagination navigation arrows (first, prev, next, last) with page info in the center.
AKA: Pager Controls, Navigation Arrows, Page Nav Group

## Relationships

**Child components (used inside this component):**
- [`.Pagination Navigation`](./.pagination-navigation.component.md)
- [`.Pagination Information`](./.pagination-information.component.md)

**Parent components (this component is used inside):**
- [`Pagination`](./pagination.component.md)

## Code contract

```typescript
interface .PaginationNavigationGroupProps {
  children?: React.ReactNode; // Accepts: .Pagination Navigation, .Pagination Information
  className?: string;
}
```

## Usage

```tsx
<.PaginationNavigationGroup>
  <.PaginationNavigation />
  <.PaginationNavigation />
  <.PaginationInformation />
  <.PaginationInformation />
</.PaginationNavigationGroup>
```

## Usage

> This component is designed to be used inside [`Pagination`](./pagination.component.md).

```tsx
<Pagination>
  <.PaginationNavigationGroup />
  <.PaginationNavigationGroup />
</Pagination>
```

## Anatomy

```
1. [Root] .Pagination Navigation Group (COMPONENT)
  2. [Container] .Pagination Navigation (INSTANCE)
    3. [Icon] Icons/ui-actions/first-page (INSTANCE)
      4. [Element] Vector (VECTOR)
  5. [Container] .Pagination Navigation (INSTANCE)
    6. [Icon] Icons/ui-actions/chevron-left (INSTANCE)
      7. [Element] Vector (VECTOR)
  8. [Container] .Pagination Information (INSTANCE)
    9. [Label] Page 1 of 3 (TEXT)
  10. [Container] .Pagination Navigation (INSTANCE)
    11. [Icon] Icons/ui-actions/chevron-right (INSTANCE)
      12. [Element] Vector (VECTOR)
  13. [Container] .Pagination Navigation (INSTANCE)
    14. [Icon] Icons/ui-actions/last-page (INSTANCE)
      15. [Element] Vector (VECTOR)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| .Pagination Navigation Group | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| .Pagination Navigation | cornerRadius | `4px` | `borderRadius.xs` | `var(--ach-borderRadius-xs)` |
| .Pagination Navigation | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| .Pagination Navigation | paddingRight | `4px` | `padding.1` | `var(--ach-padding-1)` |
| .Pagination Navigation | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| .Pagination Navigation | paddingLeft | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Icons/ui-actions/first-page | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#BDBDBD` | `pagination.nav.icon_disabled` | `var(--ach-pagination-nav-icon_disabled)` |
| .Pagination Navigation | cornerRadius | `4px` | `borderRadius.xs` | `var(--ach-borderRadius-xs)` |
| .Pagination Navigation | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| .Pagination Navigation | paddingRight | `4px` | `padding.1` | `var(--ach-padding-1)` |
| .Pagination Navigation | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| .Pagination Navigation | paddingLeft | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Icons/ui-actions/chevron-left | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#BDBDBD` | `pagination.nav.icon_disabled` | `var(--ach-pagination-nav-icon_disabled)` |
| Page 1 of 3 | fill | `#525252` | `pagination.label.text` | `var(--ach-pagination-label-text)` |
| Page 1 of 3 | fontSize | `12px` | `—` | `—` |
| .Pagination Navigation | cornerRadius | `4px` | `borderRadius.xs` | `var(--ach-borderRadius-xs)` |
| .Pagination Navigation | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| .Pagination Navigation | paddingRight | `4px` | `padding.1` | `var(--ach-padding-1)` |
| .Pagination Navigation | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| .Pagination Navigation | paddingLeft | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Icons/ui-actions/chevron-right | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `pagination.nav.icon` | `var(--ach-pagination-nav-icon)` |
| .Pagination Navigation | cornerRadius | `4px` | `borderRadius.xs` | `var(--ach-borderRadius-xs)` |
| .Pagination Navigation | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| .Pagination Navigation | paddingRight | `4px` | `padding.1` | `var(--ach-padding-1)` |
| .Pagination Navigation | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| .Pagination Navigation | paddingLeft | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Icons/ui-actions/last-page | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `pagination.nav.icon` | `var(--ach-pagination-nav-icon)` |

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
id: pagination
name: Pagination
category: navigation
figma_component_name: "Pagination"
figma_url: "https://www.figma.com/design//?node-id=1365-220"
status: draft
tokens_used:
  - pagination.background
  - pagination.border
  - padding.2
  - padding.4
  - pagination.label.text
  - pagination.dropdown.background
  - pagination.dropdown.border
  - borderRadius.sm
  - padding.1
  - pagination.dropdown.text
  - pagination.dropdown.icon
  - borderRadius.xs
  - pagination.nav.icon_disabled
  - pagination.nav.icon
child_components:
  - .pagination-information
  - .pagination-navigation-group
  - .pagination-navigation
---

# Pagination

> A navigation control for moving between pages of content, with page info and row-per-page options.
AKA: Pager, Page Navigation, Page Selector, Page Controls, Data Pagination

## Relationships

**Child components (used inside this component):**
- [`.Pagination Information`](./.pagination-information.component.md)
- [`.Pagination Navigation Group`](./.pagination-navigation-group.component.md)
- [`.Pagination Navigation`](./.pagination-navigation.component.md)

## Code contract

```typescript
interface PaginationProps {
  children?: React.ReactNode; // Accepts: .Pagination Information, .Pagination Navigation Group, .Pagination Navigation
  className?: string;
}
```

## Usage

```tsx
<Pagination>
  <.PaginationInformation />
  <.PaginationInformation />
  <.PaginationNavigationGroup />
  <.PaginationNavigationGroup />
  <.PaginationNavigation />
  <.PaginationNavigation />
</Pagination>
```

## Anatomy

```
1. [Root] 01 Pagination (COMPONENT)
  2. [Container] .Pagination Information (INSTANCE)
    3. [Label] Rows per page (TEXT)
    4. [Container] Dropdown (FRAME)
      5. [Label] 10 (TEXT)
      6. [Icon] Icons/ui-actions/expand-more (INSTANCE)
        7. [Element] Vector (VECTOR)
  8. [Container] Right Group (FRAME)
    9. [Container] .Pagination Information (INSTANCE)
      10. [Label] Page 1 of 3 (TEXT)
    11. [Container] .Pagination Navigation Group (INSTANCE)
      12. [Container] .Pagination Navigation (INSTANCE)
        13. [Icon] Icons/ui-actions/first-page (INSTANCE)
          14. [Element] Vector (VECTOR)
      15. [Container] .Pagination Navigation (INSTANCE)
        16. [Icon] Icons/ui-actions/chevron-left (INSTANCE)
          17. [Element] Vector (VECTOR)
      18. [Container] .Pagination Information (INSTANCE)
        19. [Label] Page 1 of 3 (TEXT)
      20. [Container] .Pagination Navigation (INSTANCE)
        21. [Icon] Icons/ui-actions/chevron-right (INSTANCE)
          22. [Element] Vector (VECTOR)
      23. [Container] .Pagination Navigation (INSTANCE)
        24. [Icon] Icons/ui-actions/last-page (INSTANCE)
          25. [Element] Vector (VECTOR)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| 01 Pagination | fill | `#FFFFFF` | `pagination.background` | `var(--ach-pagination-background)` |
| 01 Pagination | stroke | `#EEEEEE` | `pagination.border` | `var(--ach-pagination-border)` |
| 01 Pagination | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 01 Pagination | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 01 Pagination | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 01 Pagination | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .Pagination Information | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Rows per page | fill | `#525252` | `pagination.label.text` | `var(--ach-pagination-label-text)` |
| Rows per page | fontSize | `12px` | `—` | `—` |
| Dropdown | fill | `#FFFFFF` | `pagination.dropdown.background` | `var(--ach-pagination-dropdown-background)` |
| Dropdown | stroke | `#DCDCDC` | `pagination.dropdown.border` | `var(--ach-pagination-dropdown-border)` |
| Dropdown | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Dropdown | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Dropdown | paddingRight | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Dropdown | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Dropdown | paddingLeft | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Dropdown | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 10 | fill | `#262626` | `pagination.dropdown.text` | `var(--ach-pagination-dropdown-text)` |
| 10 | fontSize | `12px` | `—` | `—` |
| Icons/ui-actions/expand-more | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `pagination.dropdown.icon` | `var(--ach-pagination-dropdown-icon)` |
| Right Group | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Page 1 of 3 | fill | `#525252` | `pagination.label.text` | `var(--ach-pagination-label-text)` |
| Page 1 of 3 | fontSize | `12px` | `—` | `—` |
| .Pagination Navigation | cornerRadius | `4px` | `borderRadius.xs` | `var(--ach-borderRadius-xs)` |
| .Pagination Navigation | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| .Pagination Navigation | paddingRight | `4px` | `padding.1` | `var(--ach-padding-1)` |
| .Pagination Navigation | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| .Pagination Navigation | paddingLeft | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Icons/ui-actions/first-page | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#BDBDBD` | `pagination.nav.icon_disabled` | `var(--ach-pagination-nav-icon_disabled)` |
| .Pagination Navigation | cornerRadius | `4px` | `borderRadius.xs` | `var(--ach-borderRadius-xs)` |
| .Pagination Navigation | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| .Pagination Navigation | paddingRight | `4px` | `padding.1` | `var(--ach-padding-1)` |
| .Pagination Navigation | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| .Pagination Navigation | paddingLeft | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Icons/ui-actions/chevron-left | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#BDBDBD` | `pagination.nav.icon_disabled` | `var(--ach-pagination-nav-icon_disabled)` |
| .Pagination Information | paddingRight | `4px` | `padding.1` | `var(--ach-padding-1)` |
| .Pagination Information | paddingLeft | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Page 1 of 3 | fill | `#525252` | `pagination.label.text` | `var(--ach-pagination-label-text)` |
| Page 1 of 3 | fontSize | `12px` | `—` | `—` |
| .Pagination Navigation | cornerRadius | `4px` | `borderRadius.xs` | `var(--ach-borderRadius-xs)` |
| .Pagination Navigation | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| .Pagination Navigation | paddingRight | `4px` | `padding.1` | `var(--ach-padding-1)` |
| .Pagination Navigation | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| .Pagination Navigation | paddingLeft | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Icons/ui-actions/chevron-right | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `pagination.nav.icon` | `var(--ach-pagination-nav-icon)` |
| .Pagination Navigation | cornerRadius | `4px` | `borderRadius.xs` | `var(--ach-borderRadius-xs)` |
| .Pagination Navigation | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| .Pagination Navigation | paddingRight | `4px` | `padding.1` | `var(--ach-padding-1)` |
| .Pagination Navigation | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| .Pagination Navigation | paddingLeft | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Icons/ui-actions/last-page | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `pagination.nav.icon` | `var(--ach-pagination-nav-icon)` |

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
