---
id: table-header-v1.1
name: TableHeaderV1.1
category: layout
figma_component_name: "Table Header v1.1"
figma_url: "https://www.figma.com/design//?node-id=1032-12348"
status: draft
tokens_used:
  - table.headerBackground
  - padding.3
  - padding.4
  - padding.6
  - borders.borderColor
  - icon.ach-color-icon-subtle
  - padding.2
  - checkbox.default.background
  - checkbox.default.border
  - borderRadius.xs
  - checkbox.default.text
  - table.headerText
  - divider.default
child_components:
  - .header-content
parent_components:
  - table-row-v1.1
  - table-colomn-v1.1
  - table-full-table-v1.1
---

# TableHeaderV1.1

> The header row of a data table, containing column labels and optional sort controls.
AKA: Table Head, Column Header, Grid Header, Header Row, THead

## Relationships

**Child components (used inside this component):**
- [`.Header Content`](./.header-content.component.md)

**Parent components (this component is used inside):**
- [`Table Row v1.1`](./table-row-v1.1.component.md)
- [`Table Colomn v1.1`](./table-colomn-v1.1.component.md)
- [`Table Full Table v1.1`](./table-full-table-v1.1.component.md)

## Code contract

```typescript
interface TableHeaderV1.1Props {
  /** Toggle: Show Divider */
  Show Divider?: boolean;
  /** Visual variant: Background */
  Background?: 'Primary' | 'Secondary';
  /** Visual variant: State */
  State?: 'Default' | 'Hover' | 'Active';
  /** Visual variant: Size */
  Size?: 'Default' | 'Compact';
  children?: React.ReactNode; // Accepts: .Header Content
  className?: string;
}
```

## Usage

```tsx
<TableHeaderV1.1>
  <.HeaderContent />
  <.HeaderContent />
</TableHeaderV1.1>
```

## Usage

> This component is designed to be used inside [`Table Row v1.1`](./table-row-v1.1.component.md).

```tsx
<TableRowV1.1>
  <TableHeaderV1.1 />
  <TableHeaderV1.1 />
</TableRowV1.1>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Background | `Primary`, `Secondary` | `Primary` | Visual variant: Background |
| State | `Default`, `Hover`, `Active` | `Default` | Visual variant: State |
| Size | `Default`, `Compact` | `Default` | Visual variant: Size |

## Anatomy

```
1. [Root] Background=Primary, State=Default, Size=Default (COMPONENT)
  2. [Container] .Header Content (INSTANCE)
    3. [Container] Wrapper (FRAME)
      4. [Container] Left Resize Handle (FRAME)
        5. [Container] .Resize-Handle (INSTANCE)
          6. [Element] shape (RECTANGLE)
      7. [Container] Content (FRAME)
        8. [Icon] Icons/ui-actions/drag-indicator (INSTANCE)
          9. [Element] Vector (VECTOR)
        10. [Container] 01 Checkbox (INSTANCE)
          11. [Container] Checkbox (FRAME)
            12. [Element] Background (RECTANGLE)
          13. [Label] Label (TEXT)
        14. [Label] Label (TEXT)
        15. [Element] .Sorting Control (INSTANCE)
          16. [Icon] Icons/ui-actions/arrow-upward (INSTANCE)
            17. [Element] Vector (VECTOR)
      18. [Container] Right Resize Handle (FRAME)
        19. [Container] .Resize-Handle (INSTANCE)
          20. [Element] shape (RECTANGLE)
  21. [Divider] Divider (INSTANCE)
    22. [Divider] Divider (RECTANGLE)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Background=Primary, State=Default, Size=Default | fill | `#EEEEEE` | `table.headerBackground` | `var(--ach-table-headerBackground)` |
| Background=Primary, State=Default, Size=Default | paddingTop | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Background=Primary, State=Default, Size=Default | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Background=Primary, State=Default, Size=Default | paddingBottom | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Background=Primary, State=Default, Size=Default | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Background=Primary, State=Default, Size=Default | itemSpacing | `24px` | `padding.6` | `var(--ach-padding-6)` |
| .Header Content | itemSpacing | `16px` | `—` | `—` |
| Wrapper | itemSpacing | `10px` | `—` | `—` |
| .Resize-Handle | itemSpacing | `10px` | `—` | `—` |
| shape | fill | `#181D1F` | `borders.borderColor` | `var(--ach-borders-borderColor)` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Icons/ui-actions/drag-indicator | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `icon.ach-color-icon-subtle` | `var(--ach-icon-ach-color-icon-subtle)` |
| 01 Checkbox | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Checkbox | itemSpacing | `10px` | `—` | `—` |
| Background | fill | `#FFFFFF` | `checkbox.default.background` | `var(--ach-checkbox-default-background)` |
| Background | stroke | `#BDBDBD` | `checkbox.default.border` | `var(--ach-checkbox-default-border)` |
| Background | cornerRadius | `4px` | `borderRadius.xs` | `var(--ach-borderRadius-xs)` |
| Label | fill | `#262626` | `checkbox.default.text` | `var(--ach-checkbox-default-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Label | fill | `#525252` | `table.headerText` | `var(--ach-table-headerText)` |
| Label | fontSize | `14px` | `—` | `—` |
| .Sorting Control | fill | `#FFFFFF` | `—` | `—` |
| Icons/ui-actions/arrow-upward | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `icon.ach-color-icon-subtle` | `var(--ach-icon-ach-color-icon-subtle)` |
| .Resize-Handle | itemSpacing | `10px` | `—` | `—` |
| shape | fill | `#181D1F` | `borders.borderColor` | `var(--ach-borders-borderColor)` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |

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
id: .header-content
name: .HeaderContent
category: layout
figma_component_name: ".Header Content"
figma_url: "https://www.figma.com/design//?node-id=1032-12961"
status: draft
tokens_used:
  - borders.borderColor
  - icon.ach-color-icon-subtle
  - padding.2
  - checkbox.default.background
  - checkbox.default.border
  - borderRadius.xs
  - checkbox.default.text
  - text.ach-color-text-subtle
parent_components:
  - table-header-v1.1
  - table-row-v1.1
  - table-colomn-v1.1
  - table-full-table-v1.1
---

# .HeaderContent

## Relationships

**Parent components (this component is used inside):**
- [`Table Header v1.1`](./table-header-v1.1.component.md)
- [`Table Row v1.1`](./table-row-v1.1.component.md)
- [`Table Colomn v1.1`](./table-colomn-v1.1.component.md)
- [`Table Full Table v1.1`](./table-full-table-v1.1.component.md)

## Code contract

```typescript
interface .HeaderContentProps {
  /** Toggle: Show Left Resize Handle */
  Show Left Resize Handle?: boolean;
  /** Toggle: Show Right Resize Handle */
  Show Right Resize Handle?: boolean;
  /** Text content: Header Label */
  Header Label?: React.ReactNode;
  /** Visual variant: Content Type */
  Content Type?: 'Default' | 'Checkbox' | 'With Sorting' | 'With More Options' | 'Empty' | 'Checkbox with Options';
  /** Visual variant: Alignment */
  Alignment?: 'Left' | 'Right';
  children?: React.ReactNode;
  className?: string;
}
```

## Usage

> This component is designed to be used inside [`Table Header v1.1`](./table-header-v1.1.component.md).

```tsx
<TableHeaderV1.1>
  <.HeaderContent />
  <.HeaderContent />
</TableHeaderV1.1>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Content Type | `Default`, `Checkbox`, `With Sorting`, `With More Options`, `Empty`, `Checkbox with Options` | `Default` | Visual variant: Content Type |
| Alignment | `Left`, `Right` | `Left` | Visual variant: Alignment |

## Anatomy

```
1. [Root] Content Type=Default, Alignment=Left (COMPONENT)
  2. [Container] Wrapper (FRAME)
    3. [Container] Left Resize Handle (FRAME)
      4. [Container] .Resize-Handle (INSTANCE)
        5. [Element] shape (RECTANGLE)
    6. [Container] Content (FRAME)
      7. [Icon] Icons/ui-actions/drag-indicator (INSTANCE)
        8. [Element] Vector (VECTOR)
      9. [Container] 01 Checkbox (INSTANCE)
        10. [Container] Checkbox (FRAME)
          11. [Element] Background (RECTANGLE)
        12. [Label] Label (TEXT)
      13. [Label] Label (TEXT)
      14. [Element] .Sorting Control (INSTANCE)
        15. [Icon] Icons/ui-actions/arrow-upward (INSTANCE)
          16. [Element] Vector (VECTOR)
    17. [Container] Right Resize Handle (FRAME)
      18. [Container] .Resize-Handle (INSTANCE)
        19. [Element] shape (RECTANGLE)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Content Type=Default, Alignment=Left | itemSpacing | `16px` | `—` | `—` |
| Wrapper | itemSpacing | `10px` | `—` | `—` |
| .Resize-Handle | itemSpacing | `10px` | `—` | `—` |
| shape | fill | `#181D1F` | `borders.borderColor` | `var(--ach-borders-borderColor)` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Icons/ui-actions/drag-indicator | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `icon.ach-color-icon-subtle` | `var(--ach-icon-ach-color-icon-subtle)` |
| 01 Checkbox | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Checkbox | itemSpacing | `10px` | `—` | `—` |
| Background | fill | `#FFFFFF` | `checkbox.default.background` | `var(--ach-checkbox-default-background)` |
| Background | stroke | `#BDBDBD` | `checkbox.default.border` | `var(--ach-checkbox-default-border)` |
| Background | cornerRadius | `4px` | `borderRadius.xs` | `var(--ach-borderRadius-xs)` |
| Label | fill | `#262626` | `checkbox.default.text` | `var(--ach-checkbox-default-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Label | fill | `#737373` | `text.ach-color-text-subtle` | `var(--ach-text-ach-color-text-subtle)` |
| Label | fontSize | `14px` | `—` | `—` |
| .Sorting Control | fill | `#FFFFFF` | `—` | `—` |
| Icons/ui-actions/arrow-upward | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `icon.ach-color-icon-subtle` | `var(--ach-icon-ach-color-icon-subtle)` |
| .Resize-Handle | itemSpacing | `10px` | `—` | `—` |
| shape | fill | `#181D1F` | `borders.borderColor` | `var(--ach-borders-borderColor)` |

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
id: table-cell-v1.1
name: TableCellV1.1
category: navigation
figma_component_name: "Table Cell v1.1"
figma_url: "https://www.figma.com/design//?node-id=1037-15288"
status: draft
tokens_used:
  - table.background
  - padding.1
  - padding.4
  - table.rowText
  - divider.default
child_components:
  - .cell-content
parent_components:
  - table-colomn-v1.1
  - table-full-table-v1.1
---

# TableCellV1.1

> An individual data cell within a table row, displaying a single value.
AKA: Table Data, Grid Cell, Data Cell, TD, Column Cell

## Relationships

**Child components (used inside this component):**
- [`.CellContent`](./.cell-content.component.md)

**Parent components (this component is used inside):**
- [`Table Colomn v1.1`](./table-colomn-v1.1.component.md)
- [`Table Full Table v1.1`](./table-full-table-v1.1.component.md)

## Code contract

```typescript
interface TableCellV1.1Props {
  /** Toggle: Show Divider */
  Show Divider?: boolean;
  /** Visual variant: Background */
  Background?: 'Primary' | 'Secondary';
  /** Visual variant: Size */
  Size?: 'Default' | 'Compact';
  /** Visual variant: State */
  State?: 'Default' | 'Hover' | 'Active';
  children?: React.ReactNode; // Accepts: .CellContent
  className?: string;
}
```

## Usage

```tsx
<TableCellV1.1>
  <.CellContent />
  <.CellContent />
</TableCellV1.1>
```

## Usage

> This component is designed to be used inside [`Table Colomn v1.1`](./table-colomn-v1.1.component.md).

```tsx
<TableColomnV1.1>
  <TableCellV1.1 />
  <TableCellV1.1 />
</TableColomnV1.1>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Background | `Primary`, `Secondary` | `Primary` | Visual variant: Background |
| Size | `Default`, `Compact` | `Default` | Visual variant: Size |
| State | `Default`, `Hover`, `Active` | `Default` | Visual variant: State |

## Anatomy

```
1. [Root] Background=Primary, Size=Default, State=Default (COMPONENT)
  2. [Container] .CellContent (INSTANCE)
    3. [Container] Content (FRAME)
      4. [Label] Label (TEXT)
  5. [Divider] Divider (INSTANCE)
    6. [Divider] Divider (RECTANGLE)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Background=Primary, Size=Default, State=Default | fill | `#FFFFFF` | `table.background` | `var(--ach-table-background)` |
| Background=Primary, Size=Default, State=Default | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Background=Primary, Size=Default, State=Default | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Background=Primary, Size=Default, State=Default | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Background=Primary, Size=Default, State=Default | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |

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
id: .cell-content
name: .CellContent
category: primitive
figma_component_name: ".CellContent"
figma_url: "https://www.figma.com/design//?node-id=1037-15357"
status: draft
tokens_used:
  - text.ach-color-text-default
parent_components:
  - table-cell-v1.1
  - table-colomn-v1.1
  - table-full-table-v1.1
---

# .CellContent

## Relationships

**Parent components (this component is used inside):**
- [`Table Cell v1.1`](./table-cell-v1.1.component.md)
- [`Table Colomn v1.1`](./table-colomn-v1.1.component.md)
- [`Table Full Table v1.1`](./table-full-table-v1.1.component.md)

## Code contract

```typescript
interface .CellContentProps {
  /** Text content: Label */
  Label?: React.ReactNode;
  /** Text content: Subtitle */
  Subtitle?: React.ReactNode;
  /** Slot: Action Instance */
  Action Instance?: React.ReactNode;
  /** Toggle: Show Label */
  Show Label?: boolean;
  /** Toggle: Show Subtitle */
  Show Subtitle?: boolean;
  /** Visual variant: Content Type */
  Content Type?: 'Default' | 'Two Lines' | 'Right Aligned Default' | 'Right Aligned Two Lines' | 'Action' | 'Avatar' | 'Badge' | 'Button' | 'Input' | 'Slot' | 'Checkbox' | 'Dropdown' | 'Empty' | 'Link';
  children?: React.ReactNode;
  className?: string;
}
```

## Usage

> This component is designed to be used inside [`Table Cell v1.1`](./table-cell-v1.1.component.md).

```tsx
<TableCellV1.1>
  <.CellContent />
  <.CellContent />
</TableCellV1.1>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Content Type | `Default`, `Two Lines`, `Right Aligned Default`, `Right Aligned Two Lines`, `Action`, `Avatar`, `Badge`, `Button`, `Input`, `Slot`, `Checkbox`, `Dropdown`, `Empty`, `Link` | `Default` | Visual variant: Content Type |

## Anatomy

```
1. [Root] Content Type=Default (COMPONENT)
  2. [Container] Content (FRAME)
    3. [Label] Label (TEXT)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Content Type=Default | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `text.ach-color-text-default` | `var(--ach-text-ach-color-text-default)` |
| Label | fontSize | `14px` | `—` | `—` |

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
id: table-row-v1.1
name: TableRowV1.1
category: navigation
figma_component_name: "Table Row v1.1"
figma_url: "https://www.figma.com/design//?node-id=1037-16648"
status: draft
tokens_used:
  - bg.ach-color-bg-surface
  - padding.3
  - padding.4
  - padding.6
  - borders.borderColor
  - icon.ach-color-icon-subtle
  - padding.2
  - checkbox.default.background
  - checkbox.default.border
  - borderRadius.xs
  - checkbox.default.text
  - table.headerText
  - divider.default
child_components:
  - table-header-v1.1
  - .header-content
parent_components:
  - table-full-table-v1.1
---

# TableRowV1.1

> A horizontal row of cells within a table, representing a single data record.
AKA: Table Record, Data Row, Grid Row, TR, Table Entry

## Relationships

**Child components (used inside this component):**
- [`Table Header v1.1`](./table-header-v1.1.component.md)
- [`.Header Content`](./.header-content.component.md)

**Parent components (this component is used inside):**
- [`Table Full Table v1.1`](./table-full-table-v1.1.component.md)

## Code contract

```typescript
interface TableRowV1.1Props {
  /** Visual variant: Type */
  Type?: 'Header' | 'Cell' | 'Heade';
  /** Visual variant: Size */
  Size?: 'Default' | 'Compact';
  children?: React.ReactNode; // Accepts: Table Header v1.1, .Header Content
  className?: string;
}
```

## Usage

```tsx
<TableRowV1.1>
  <TableHeaderV1.1 />
  <TableHeaderV1.1 />
  <.HeaderContent />
  <.HeaderContent />
</TableRowV1.1>
```

## Usage

> This component is designed to be used inside [`Table Full Table v1.1`](./table-full-table-v1.1.component.md).

```tsx
<TableFullTableV1.1>
  <TableRowV1.1 />
  <TableRowV1.1 />
</TableFullTableV1.1>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Type | `Header`, `Cell`, `Heade` | `Header` | Visual variant: Type |
| Size | `Default`, `Compact` | `Default` | Visual variant: Size |

## Anatomy

```
1. [Root] Type=Header, Size=Default (COMPONENT)
  2. [Container] Slot (SLOT)
    3. [Container] 01 Table Header v1.1 (INSTANCE)
      4. [Container] .Header Content (INSTANCE)
        5. [Container] Wrapper (FRAME)
          6. [Container] Left Resize Handle (FRAME)
            7. [Container] .Resize-Handle (INSTANCE)
              8. [Element] shape (RECTANGLE)
          9. [Container] Content (FRAME)
            10. [Icon] Icons/ui-actions/drag-indicator (INSTANCE)
              11. [Element] Vector (VECTOR)
            12. [Container] 01 Checkbox (INSTANCE)
              13. [Container] Checkbox (FRAME)
                14. [Element] Background (RECTANGLE)
              15. [Label] Label (TEXT)
            16. [Label] Label (TEXT)
            17. [Element] .Sorting Control (INSTANCE)
              18. [Icon] Icons/ui-actions/arrow-upward (INSTANCE)
                19. [Element] Vector (VECTOR)
          20. [Container] Right Resize Handle (FRAME)
            21. [Container] .Resize-Handle (INSTANCE)
              22. [Element] shape (RECTANGLE)
      23. [Divider] Divider (INSTANCE)
        24. [Divider] Divider (RECTANGLE)
    25. [Container] 01 Table Header v1.1 (INSTANCE)
      26. [Container] .Header Content (INSTANCE)
        27. [Container] Wrapper (FRAME)
          28. [Container] Left Resize Handle (FRAME)
            29. [Container] .Resize-Handle (INSTANCE)
              30. [Element] shape (RECTANGLE)
          31. [Container] Content (FRAME)
            32. [Icon] Icons/ui-actions/drag-indicator (INSTANCE)
              33. [Element] Vector (VECTOR)
            34. [Container] 01 Checkbox (INSTANCE)
              35. [Container] Checkbox (FRAME)
                36. [Element] Background (RECTANGLE)
              37. [Label] Label (TEXT)
            38. [Label] Label (TEXT)
            39. [Element] .Sorting Control (INSTANCE)
              40. [Icon] Icons/ui-actions/arrow-upward (INSTANCE)
                41. [Element] Vector (VECTOR)
          42. [Container] Right Resize Handle (FRAME)
            43. [Container] .Resize-Handle (INSTANCE)
              44. [Element] shape (RECTANGLE)
      45. [Divider] Divider (INSTANCE)
        46. [Divider] Divider (RECTANGLE)
    47. [Container] 01 Table Header v1.1 (INSTANCE)
      48. [Container] .Header Content (INSTANCE)
        49. [Container] Wrapper (FRAME)
          50. [Container] Left Resize Handle (FRAME)
            51. [Container] .Resize-Handle (INSTANCE)
              52. [Element] shape (RECTANGLE)
          53. [Container] Content (FRAME)
            54. [Icon] Icons/ui-actions/drag-indicator (INSTANCE)
              55. [Element] Vector (VECTOR)
            56. [Container] 01 Checkbox (INSTANCE)
              57. [Container] Checkbox (FRAME)
                58. [Element] Background (RECTANGLE)
              59. [Label] Label (TEXT)
            60. [Label] Label (TEXT)
            61. [Element] .Sorting Control (INSTANCE)
              62. [Icon] Icons/ui-actions/arrow-upward (INSTANCE)
                63. [Element] Vector (VECTOR)
          64. [Container] Right Resize Handle (FRAME)
            65. [Container] .Resize-Handle (INSTANCE)
              66. [Element] shape (RECTANGLE)
      67. [Divider] Divider (INSTANCE)
        68. [Divider] Divider (RECTANGLE)
    69. [Container] 01 Table Header v1.1 (INSTANCE)
      70. [Container] .Header Content (INSTANCE)
        71. [Container] Wrapper (FRAME)
          72. [Container] Left Resize Handle (FRAME)
            73. [Container] .Resize-Handle (INSTANCE)
              74. [Element] shape (RECTANGLE)
          75. [Container] Content (FRAME)
            76. [Icon] Icons/ui-actions/drag-indicator (INSTANCE)
              77. [Element] Vector (VECTOR)
            78. [Container] 01 Checkbox (INSTANCE)
              79. [Container] Checkbox (FRAME)
                80. [Element] Background (RECTANGLE)
              81. [Label] Label (TEXT)
            82. [Label] Label (TEXT)
            83. [Element] .Sorting Control (INSTANCE)
              84. [Icon] Icons/ui-actions/arrow-upward (INSTANCE)
                85. [Element] Vector (VECTOR)
          86. [Container] Right Resize Handle (FRAME)
            87. [Container] .Resize-Handle (INSTANCE)
              88. [Element] shape (RECTANGLE)
      89. [Divider] Divider (INSTANCE)
        90. [Divider] Divider (RECTANGLE)
    91. [Container] 01 Table Header v1.1 (INSTANCE)
      92. [Container] .Header Content (INSTANCE)
        93. [Container] Wrapper (FRAME)
          94. [Container] Left Resize Handle (FRAME)
            95. [Container] .Resize-Handle (INSTANCE)
              96. [Element] shape (RECTANGLE)
          97. [Container] Content (FRAME)
            98. [Icon] Icons/ui-actions/drag-indicator (INSTANCE)
              99. [Element] Vector (VECTOR)
            100. [Container] 01 Checkbox (INSTANCE)
              101. [Container] Checkbox (FRAME)
                102. [Element] Background (RECTANGLE)
              103. [Label] Label (TEXT)
            104. [Label] Label (TEXT)
            105. [Element] .Sorting Control (INSTANCE)
              106. [Icon] Icons/ui-actions/arrow-upward (INSTANCE)
                107. [Element] Vector (VECTOR)
          108. [Container] Right Resize Handle (FRAME)
            109. [Container] .Resize-Handle (INSTANCE)
              110. [Element] shape (RECTANGLE)
      111. [Divider] Divider (INSTANCE)
        112. [Divider] Divider (RECTANGLE)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Type=Header, Size=Default | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 01 Table Header v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 01 Table Header v1.1 | paddingTop | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 01 Table Header v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 01 Table Header v1.1 | paddingBottom | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 01 Table Header v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 01 Table Header v1.1 | itemSpacing | `24px` | `padding.6` | `var(--ach-padding-6)` |
| .Header Content | itemSpacing | `16px` | `—` | `—` |
| Wrapper | itemSpacing | `10px` | `—` | `—` |
| .Resize-Handle | itemSpacing | `10px` | `—` | `—` |
| shape | fill | `#181D1F` | `borders.borderColor` | `var(--ach-borders-borderColor)` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Icons/ui-actions/drag-indicator | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `icon.ach-color-icon-subtle` | `var(--ach-icon-ach-color-icon-subtle)` |
| 01 Checkbox | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Checkbox | itemSpacing | `10px` | `—` | `—` |
| Background | fill | `#FFFFFF` | `checkbox.default.background` | `var(--ach-checkbox-default-background)` |
| Background | stroke | `#BDBDBD` | `checkbox.default.border` | `var(--ach-checkbox-default-border)` |
| Background | cornerRadius | `4px` | `borderRadius.xs` | `var(--ach-borderRadius-xs)` |
| Label | fill | `#262626` | `checkbox.default.text` | `var(--ach-checkbox-default-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Label | fill | `#525252` | `table.headerText` | `var(--ach-table-headerText)` |
| Label | fontSize | `14px` | `—` | `—` |
| .Sorting Control | fill | `#FFFFFF` | `—` | `—` |
| Icons/ui-actions/arrow-upward | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `icon.ach-color-icon-subtle` | `var(--ach-icon-ach-color-icon-subtle)` |
| .Resize-Handle | itemSpacing | `10px` | `—` | `—` |
| shape | fill | `#181D1F` | `borders.borderColor` | `var(--ach-borders-borderColor)` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 01 Table Header v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 01 Table Header v1.1 | paddingTop | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 01 Table Header v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 01 Table Header v1.1 | paddingBottom | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 01 Table Header v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 01 Table Header v1.1 | itemSpacing | `24px` | `padding.6` | `var(--ach-padding-6)` |
| .Header Content | itemSpacing | `16px` | `—` | `—` |
| Wrapper | itemSpacing | `10px` | `—` | `—` |
| .Resize-Handle | itemSpacing | `10px` | `—` | `—` |
| shape | fill | `#181D1F` | `borders.borderColor` | `var(--ach-borders-borderColor)` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Icons/ui-actions/drag-indicator | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `icon.ach-color-icon-subtle` | `var(--ach-icon-ach-color-icon-subtle)` |
| 01 Checkbox | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Checkbox | itemSpacing | `10px` | `—` | `—` |
| Background | fill | `#FFFFFF` | `checkbox.default.background` | `var(--ach-checkbox-default-background)` |
| Background | stroke | `#BDBDBD` | `checkbox.default.border` | `var(--ach-checkbox-default-border)` |
| Background | cornerRadius | `4px` | `borderRadius.xs` | `var(--ach-borderRadius-xs)` |
| Label | fill | `#262626` | `checkbox.default.text` | `var(--ach-checkbox-default-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Label | fill | `#525252` | `table.headerText` | `var(--ach-table-headerText)` |
| Label | fontSize | `14px` | `—` | `—` |
| .Sorting Control | fill | `#FFFFFF` | `—` | `—` |
| Icons/ui-actions/arrow-upward | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `icon.ach-color-icon-subtle` | `var(--ach-icon-ach-color-icon-subtle)` |
| .Resize-Handle | itemSpacing | `10px` | `—` | `—` |
| shape | fill | `#181D1F` | `borders.borderColor` | `var(--ach-borders-borderColor)` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 01 Table Header v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 01 Table Header v1.1 | paddingTop | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 01 Table Header v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 01 Table Header v1.1 | paddingBottom | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 01 Table Header v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 01 Table Header v1.1 | itemSpacing | `24px` | `padding.6` | `var(--ach-padding-6)` |
| .Header Content | itemSpacing | `16px` | `—` | `—` |
| Wrapper | itemSpacing | `10px` | `—` | `—` |
| .Resize-Handle | itemSpacing | `10px` | `—` | `—` |
| shape | fill | `#181D1F` | `borders.borderColor` | `var(--ach-borders-borderColor)` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Icons/ui-actions/drag-indicator | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `icon.ach-color-icon-subtle` | `var(--ach-icon-ach-color-icon-subtle)` |
| 01 Checkbox | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Checkbox | itemSpacing | `10px` | `—` | `—` |
| Background | fill | `#FFFFFF` | `checkbox.default.background` | `var(--ach-checkbox-default-background)` |
| Background | stroke | `#BDBDBD` | `checkbox.default.border` | `var(--ach-checkbox-default-border)` |
| Background | cornerRadius | `4px` | `borderRadius.xs` | `var(--ach-borderRadius-xs)` |
| Label | fill | `#262626` | `checkbox.default.text` | `var(--ach-checkbox-default-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Label | fill | `#525252` | `table.headerText` | `var(--ach-table-headerText)` |
| Label | fontSize | `14px` | `—` | `—` |
| .Sorting Control | fill | `#FFFFFF` | `—` | `—` |
| Icons/ui-actions/arrow-upward | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `icon.ach-color-icon-subtle` | `var(--ach-icon-ach-color-icon-subtle)` |
| .Resize-Handle | itemSpacing | `10px` | `—` | `—` |
| shape | fill | `#181D1F` | `borders.borderColor` | `var(--ach-borders-borderColor)` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 01 Table Header v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 01 Table Header v1.1 | paddingTop | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 01 Table Header v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 01 Table Header v1.1 | paddingBottom | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 01 Table Header v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 01 Table Header v1.1 | itemSpacing | `24px` | `padding.6` | `var(--ach-padding-6)` |
| .Header Content | itemSpacing | `16px` | `—` | `—` |
| Wrapper | itemSpacing | `10px` | `—` | `—` |
| .Resize-Handle | itemSpacing | `10px` | `—` | `—` |
| shape | fill | `#181D1F` | `borders.borderColor` | `var(--ach-borders-borderColor)` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Icons/ui-actions/drag-indicator | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `icon.ach-color-icon-subtle` | `var(--ach-icon-ach-color-icon-subtle)` |
| 01 Checkbox | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Checkbox | itemSpacing | `10px` | `—` | `—` |
| Background | fill | `#FFFFFF` | `checkbox.default.background` | `var(--ach-checkbox-default-background)` |
| Background | stroke | `#BDBDBD` | `checkbox.default.border` | `var(--ach-checkbox-default-border)` |
| Background | cornerRadius | `4px` | `borderRadius.xs` | `var(--ach-borderRadius-xs)` |
| Label | fill | `#262626` | `checkbox.default.text` | `var(--ach-checkbox-default-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Label | fill | `#525252` | `table.headerText` | `var(--ach-table-headerText)` |
| Label | fontSize | `14px` | `—` | `—` |
| .Sorting Control | fill | `#FFFFFF` | `—` | `—` |
| Icons/ui-actions/arrow-upward | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `icon.ach-color-icon-subtle` | `var(--ach-icon-ach-color-icon-subtle)` |
| .Resize-Handle | itemSpacing | `10px` | `—` | `—` |
| shape | fill | `#181D1F` | `borders.borderColor` | `var(--ach-borders-borderColor)` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 01 Table Header v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 01 Table Header v1.1 | paddingTop | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 01 Table Header v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 01 Table Header v1.1 | paddingBottom | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 01 Table Header v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 01 Table Header v1.1 | itemSpacing | `24px` | `padding.6` | `var(--ach-padding-6)` |
| .Header Content | itemSpacing | `16px` | `—` | `—` |
| Wrapper | itemSpacing | `10px` | `—` | `—` |
| .Resize-Handle | itemSpacing | `10px` | `—` | `—` |
| shape | fill | `#181D1F` | `borders.borderColor` | `var(--ach-borders-borderColor)` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Icons/ui-actions/drag-indicator | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `icon.ach-color-icon-subtle` | `var(--ach-icon-ach-color-icon-subtle)` |
| 01 Checkbox | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Checkbox | itemSpacing | `10px` | `—` | `—` |
| Background | fill | `#FFFFFF` | `checkbox.default.background` | `var(--ach-checkbox-default-background)` |
| Background | stroke | `#BDBDBD` | `checkbox.default.border` | `var(--ach-checkbox-default-border)` |
| Background | cornerRadius | `4px` | `borderRadius.xs` | `var(--ach-borderRadius-xs)` |
| Label | fill | `#262626` | `checkbox.default.text` | `var(--ach-checkbox-default-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Label | fill | `#525252` | `table.headerText` | `var(--ach-table-headerText)` |
| Label | fontSize | `14px` | `—` | `—` |
| .Sorting Control | fill | `#FFFFFF` | `—` | `—` |
| Icons/ui-actions/arrow-upward | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `icon.ach-color-icon-subtle` | `var(--ach-icon-ach-color-icon-subtle)` |
| .Resize-Handle | itemSpacing | `10px` | `—` | `—` |
| shape | fill | `#181D1F` | `borders.borderColor` | `var(--ach-borders-borderColor)` |
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
id: table-colomn-v1.1
name: TableColomnV1.1
category: navigation
figma_component_name: "Table Colomn v1.1"
figma_url: "https://www.figma.com/design//?node-id=1037-16980"
status: draft
tokens_used:
  - bg.ach-color-bg-surface
  - padding.3
  - padding.4
  - padding.6
  - borders.borderColor
  - icon.ach-color-icon-subtle
  - padding.2
  - checkbox.default.background
  - checkbox.default.border
  - borderRadius.xs
  - checkbox.default.text
  - table.headerText
  - divider.default
  - padding.1
  - table.rowText
child_components:
  - table-header-v1.1
  - .header-content
  - table-cell-v1.1
  - .cell-content
---

# TableColomnV1.1

> A vertical column within a table, stacking header and data cells.
AKA: Table Column, Data Column, Grid Column, Column Stack

## Relationships

**Child components (used inside this component):**
- [`Table Header v1.1`](./table-header-v1.1.component.md)
- [`.Header Content`](./.header-content.component.md)
- [`Table Cell v1.1`](./table-cell-v1.1.component.md)
- [`.CellContent`](./.cell-content.component.md)

## Code contract

```typescript
interface TableColomnV1.1Props {
  /** Visual variant: With Header */
  With Header?: 'True' | 'False' | 'With Header3' | 'With Header4';
  /** Visual variant: Size */
  Size?: 'Default' | 'Compact';
  children?: React.ReactNode; // Accepts: Table Header v1.1, .Header Content, Table Cell v1.1, .CellContent
  className?: string;
}
```

## Usage

```tsx
<TableColomnV1.1>
  <TableHeaderV1.1 />
  <TableHeaderV1.1 />
  <.HeaderContent />
  <.HeaderContent />
  <TableCellV1.1 />
  <TableCellV1.1 />
  <.CellContent />
  <.CellContent />
</TableColomnV1.1>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| With Header | `True`, `False`, `With Header3`, `With Header4` | `True` | Visual variant: With Header |
| Size | `Default`, `Compact` | `Default` | Visual variant: Size |

## Anatomy

```
1. [Root] With Header=True, Size=Default (COMPONENT)
  2. [Container] Slot (SLOT)
    3. [Container] 01 Table Header v1.1 (INSTANCE)
      4. [Container] .Header Content (INSTANCE)
        5. [Container] Wrapper (FRAME)
          6. [Container] Left Resize Handle (FRAME)
            7. [Container] .Resize-Handle (INSTANCE)
              8. [Element] shape (RECTANGLE)
          9. [Container] Content (FRAME)
            10. [Icon] Icons/ui-actions/drag-indicator (INSTANCE)
              11. [Element] Vector (VECTOR)
            12. [Container] 01 Checkbox (INSTANCE)
              13. [Container] Checkbox (FRAME)
                14. [Element] Background (RECTANGLE)
              15. [Label] Label (TEXT)
            16. [Label] Label (TEXT)
            17. [Element] .Sorting Control (INSTANCE)
              18. [Icon] Icons/ui-actions/arrow-upward (INSTANCE)
                19. [Element] Vector (VECTOR)
          20. [Container] Right Resize Handle (FRAME)
            21. [Container] .Resize-Handle (INSTANCE)
              22. [Element] shape (RECTANGLE)
      23. [Divider] Divider (INSTANCE)
        24. [Divider] Divider (RECTANGLE)
    25. [Container] 02 Table Cell v1.1 (INSTANCE)
      26. [Container] .CellContent (INSTANCE)
        27. [Container] Content (FRAME)
          28. [Label] Label (TEXT)
      29. [Divider] Divider (INSTANCE)
        30. [Divider] Divider (RECTANGLE)
    31. [Container] 02 Table Cell v1.1 (INSTANCE)
      32. [Container] .CellContent (INSTANCE)
        33. [Container] Content (FRAME)
          34. [Label] Label (TEXT)
      35. [Divider] Divider (INSTANCE)
        36. [Divider] Divider (RECTANGLE)
    37. [Container] 02 Table Cell v1.1 (INSTANCE)
      38. [Container] .CellContent (INSTANCE)
        39. [Container] Content (FRAME)
          40. [Label] Label (TEXT)
      41. [Divider] Divider (INSTANCE)
        42. [Divider] Divider (RECTANGLE)
    43. [Container] 02 Table Cell v1.1 (INSTANCE)
      44. [Container] .CellContent (INSTANCE)
        45. [Container] Content (FRAME)
          46. [Label] Label (TEXT)
      47. [Divider] Divider (INSTANCE)
        48. [Divider] Divider (RECTANGLE)
    49. [Container] 02 Table Cell v1.1 (INSTANCE)
      50. [Container] .CellContent (INSTANCE)
        51. [Container] Content (FRAME)
          52. [Label] Label (TEXT)
      53. [Divider] Divider (INSTANCE)
        54. [Divider] Divider (RECTANGLE)
    55. [Container] 02 Table Cell v1.1 (INSTANCE)
      56. [Container] .CellContent (INSTANCE)
        57. [Container] Content (FRAME)
          58. [Label] Label (TEXT)
      59. [Divider] Divider (INSTANCE)
        60. [Divider] Divider (RECTANGLE)
    61. [Container] 02 Table Cell v1.1 (INSTANCE)
      62. [Container] .CellContent (INSTANCE)
        63. [Container] Content (FRAME)
          64. [Label] Label (TEXT)
      65. [Divider] Divider (INSTANCE)
        66. [Divider] Divider (RECTANGLE)
    67. [Container] 02 Table Cell v1.1 (INSTANCE)
      68. [Container] .CellContent (INSTANCE)
        69. [Container] Content (FRAME)
          70. [Label] Label (TEXT)
      71. [Divider] Divider (INSTANCE)
        72. [Divider] Divider (RECTANGLE)
    73. [Container] 02 Table Cell v1.1 (INSTANCE)
      74. [Container] .CellContent (INSTANCE)
        75. [Container] Content (FRAME)
          76. [Label] Label (TEXT)
      77. [Divider] Divider (INSTANCE)
        78. [Divider] Divider (RECTANGLE)
    79. [Container] 02 Table Cell v1.1 (INSTANCE)
      80. [Container] .CellContent (INSTANCE)
        81. [Container] Content (FRAME)
          82. [Label] Label (TEXT)
      83. [Divider] Divider (INSTANCE)
        84. [Divider] Divider (RECTANGLE)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| With Header=True, Size=Default | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 01 Table Header v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 01 Table Header v1.1 | paddingTop | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 01 Table Header v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 01 Table Header v1.1 | paddingBottom | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 01 Table Header v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 01 Table Header v1.1 | itemSpacing | `24px` | `padding.6` | `var(--ach-padding-6)` |
| .Header Content | itemSpacing | `16px` | `—` | `—` |
| Wrapper | itemSpacing | `10px` | `—` | `—` |
| .Resize-Handle | itemSpacing | `10px` | `—` | `—` |
| shape | fill | `#181D1F` | `borders.borderColor` | `var(--ach-borders-borderColor)` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Icons/ui-actions/drag-indicator | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `icon.ach-color-icon-subtle` | `var(--ach-icon-ach-color-icon-subtle)` |
| 01 Checkbox | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Checkbox | itemSpacing | `10px` | `—` | `—` |
| Background | fill | `#FFFFFF` | `checkbox.default.background` | `var(--ach-checkbox-default-background)` |
| Background | stroke | `#BDBDBD` | `checkbox.default.border` | `var(--ach-checkbox-default-border)` |
| Background | cornerRadius | `4px` | `borderRadius.xs` | `var(--ach-borderRadius-xs)` |
| Label | fill | `#262626` | `checkbox.default.text` | `var(--ach-checkbox-default-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Label | fill | `#525252` | `table.headerText` | `var(--ach-table-headerText)` |
| Label | fontSize | `14px` | `—` | `—` |
| .Sorting Control | fill | `#FFFFFF` | `—` | `—` |
| Icons/ui-actions/arrow-upward | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `icon.ach-color-icon-subtle` | `var(--ach-icon-ach-color-icon-subtle)` |
| .Resize-Handle | itemSpacing | `10px` | `—` | `—` |
| shape | fill | `#181D1F` | `borders.borderColor` | `var(--ach-borders-borderColor)` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
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
id: table-full-table-v1.1
name: TableFullTableV1.1
category: navigation
figma_component_name: "Table Full Table v1.1"
figma_url: "https://www.figma.com/design//?node-id=1037-17241"
status: draft
tokens_used:
  - bg.ach-color-bg-surface
  - padding.3
  - padding.4
  - padding.6
  - borders.borderColor
  - icon.ach-color-icon-subtle
  - padding.2
  - checkbox.default.background
  - checkbox.default.border
  - borderRadius.xs
  - checkbox.default.text
  - table.headerText
  - divider.default
  - padding.1
  - table.rowText
child_components:
  - table-row-v1.1
  - table-header-v1.1
  - .header-content
  - table-cell-v1.1
  - .cell-content
---

# TableFullTableV1.1

> A complete pre-assembled data table with header, rows, and cells ready for content.
AKA: Data Table, Data Grid, Grid, Spreadsheet, Table View, Record List

## Relationships

**Child components (used inside this component):**
- [`Table Row v1.1`](./table-row-v1.1.component.md)
- [`Table Header v1.1`](./table-header-v1.1.component.md)
- [`.Header Content`](./.header-content.component.md)
- [`Table Cell v1.1`](./table-cell-v1.1.component.md)
- [`.CellContent`](./.cell-content.component.md)

## Code contract

```typescript
interface TableFullTableV1.1Props {
  /** Visual variant: Orientations */
  Orientations?: 'Colomn Based' | 'Rows Based';
  /** Visual variant: Size */
  Size?: 'Default' | 'Compact';
  children?: React.ReactNode; // Accepts: Table Row v1.1, Table Header v1.1, .Header Content, Table Cell v1.1, .CellContent
  className?: string;
}
```

## Usage

```tsx
<TableFullTableV1.1>
  <TableRowV1.1 />
  <TableRowV1.1 />
  <TableHeaderV1.1 />
  <TableHeaderV1.1 />
  <.HeaderContent />
  <.HeaderContent />
  <TableCellV1.1 />
  <TableCellV1.1 />
  <.CellContent />
  <.CellContent />
</TableFullTableV1.1>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Orientations | `Colomn Based`, `Rows Based` | `Rows Based` | Visual variant: Orientations |
| Size | `Default`, `Compact` | `Default` | Visual variant: Size |

## Anatomy

```
1. [Root] Orientations=Rows Based, Size=Default (COMPONENT)
  2. [Container] Slot (SLOT)
    3. [Container] 03 Table Row v1.1 (INSTANCE)
      4. [Container] Slot (SLOT)
        5. [Container] 01 Table Header v1.1 (INSTANCE)
          6. [Container] .Header Content (INSTANCE)
            7. [Container] Wrapper (FRAME)
              8. [Container] Left Resize Handle (FRAME)
                9. [Container] .Resize-Handle (INSTANCE)
                  10. [Element] shape (RECTANGLE)
              11. [Container] Content (FRAME)
                12. [Icon] Icons/ui-actions/drag-indicator (INSTANCE)
                  13. [Element] Vector (VECTOR)
                14. [Container] 01 Checkbox (INSTANCE)
                  15. [Container] Checkbox (FRAME)
                    16. [Element] Background (RECTANGLE)
                  17. [Label] Label (TEXT)
                18. [Label] Label (TEXT)
                19. [Element] .Sorting Control (INSTANCE)
                  20. [Icon] Icons/ui-actions/arrow-upward (INSTANCE)
                    21. [Element] Vector (VECTOR)
              22. [Container] Right Resize Handle (FRAME)
                23. [Container] .Resize-Handle (INSTANCE)
                  24. [Element] shape (RECTANGLE)
          25. [Divider] Divider (INSTANCE)
            26. [Divider] Divider (RECTANGLE)
        27. [Container] 01 Table Header v1.1 (INSTANCE)
          28. [Container] .Header Content (INSTANCE)
            29. [Container] Wrapper (FRAME)
              30. [Container] Left Resize Handle (FRAME)
                31. [Container] .Resize-Handle (INSTANCE)
                  32. [Element] shape (RECTANGLE)
              33. [Container] Content (FRAME)
                34. [Icon] Icons/ui-actions/drag-indicator (INSTANCE)
                  35. [Element] Vector (VECTOR)
                36. [Container] 01 Checkbox (INSTANCE)
                  37. [Container] Checkbox (FRAME)
                    38. [Element] Background (RECTANGLE)
                  39. [Label] Label (TEXT)
                40. [Label] Label (TEXT)
                41. [Element] .Sorting Control (INSTANCE)
                  42. [Icon] Icons/ui-actions/arrow-upward (INSTANCE)
                    43. [Element] Vector (VECTOR)
              44. [Container] Right Resize Handle (FRAME)
                45. [Container] .Resize-Handle (INSTANCE)
                  46. [Element] shape (RECTANGLE)
          47. [Divider] Divider (INSTANCE)
            48. [Divider] Divider (RECTANGLE)
        49. [Container] 01 Table Header v1.1 (INSTANCE)
          50. [Container] .Header Content (INSTANCE)
            51. [Container] Wrapper (FRAME)
              52. [Container] Left Resize Handle (FRAME)
                53. [Container] .Resize-Handle (INSTANCE)
                  54. [Element] shape (RECTANGLE)
              55. [Container] Content (FRAME)
                56. [Icon] Icons/ui-actions/drag-indicator (INSTANCE)
                  57. [Element] Vector (VECTOR)
                58. [Container] 01 Checkbox (INSTANCE)
                  59. [Container] Checkbox (FRAME)
                    60. [Element] Background (RECTANGLE)
                  61. [Label] Label (TEXT)
                62. [Label] Label (TEXT)
                63. [Element] .Sorting Control (INSTANCE)
                  64. [Icon] Icons/ui-actions/arrow-upward (INSTANCE)
                    65. [Element] Vector (VECTOR)
              66. [Container] Right Resize Handle (FRAME)
                67. [Container] .Resize-Handle (INSTANCE)
                  68. [Element] shape (RECTANGLE)
          69. [Divider] Divider (INSTANCE)
            70. [Divider] Divider (RECTANGLE)
        71. [Container] 01 Table Header v1.1 (INSTANCE)
          72. [Container] .Header Content (INSTANCE)
            73. [Container] Wrapper (FRAME)
              74. [Container] Left Resize Handle (FRAME)
                75. [Container] .Resize-Handle (INSTANCE)
                  76. [Element] shape (RECTANGLE)
              77. [Container] Content (FRAME)
                78. [Icon] Icons/ui-actions/drag-indicator (INSTANCE)
                  79. [Element] Vector (VECTOR)
                80. [Container] 01 Checkbox (INSTANCE)
                  81. [Container] Checkbox (FRAME)
                    82. [Element] Background (RECTANGLE)
                  83. [Label] Label (TEXT)
                84. [Label] Label (TEXT)
                85. [Element] .Sorting Control (INSTANCE)
                  86. [Icon] Icons/ui-actions/arrow-upward (INSTANCE)
                    87. [Element] Vector (VECTOR)
              88. [Container] Right Resize Handle (FRAME)
                89. [Container] .Resize-Handle (INSTANCE)
                  90. [Element] shape (RECTANGLE)
          91. [Divider] Divider (INSTANCE)
            92. [Divider] Divider (RECTANGLE)
        93. [Container] 01 Table Header v1.1 (INSTANCE)
          94. [Container] .Header Content (INSTANCE)
            95. [Container] Wrapper (FRAME)
              96. [Container] Left Resize Handle (FRAME)
                97. [Container] .Resize-Handle (INSTANCE)
                  98. [Element] shape (RECTANGLE)
              99. [Container] Content (FRAME)
                100. [Icon] Icons/ui-actions/drag-indicator (INSTANCE)
                  101. [Element] Vector (VECTOR)
                102. [Container] 01 Checkbox (INSTANCE)
                  103. [Container] Checkbox (FRAME)
                    104. [Element] Background (RECTANGLE)
                  105. [Label] Label (TEXT)
                106. [Label] Label (TEXT)
                107. [Element] .Sorting Control (INSTANCE)
                  108. [Icon] Icons/ui-actions/arrow-upward (INSTANCE)
                    109. [Element] Vector (VECTOR)
              110. [Container] Right Resize Handle (FRAME)
                111. [Container] .Resize-Handle (INSTANCE)
                  112. [Element] shape (RECTANGLE)
          113. [Divider] Divider (INSTANCE)
            114. [Divider] Divider (RECTANGLE)
    115. [Container] 03 Table Row v1.1 (INSTANCE)
      116. [Container] Slot (SLOT)
        117. [Container] 02 Table Cell v1.1 (INSTANCE)
          118. [Container] .CellContent (INSTANCE)
            119. [Container] Content (FRAME)
              120. [Label] Label (TEXT)
          121. [Divider] Divider (INSTANCE)
            122. [Divider] Divider (RECTANGLE)
        123. [Container] 02 Table Cell v1.1 (INSTANCE)
          124. [Container] .CellContent (INSTANCE)
            125. [Container] Content (FRAME)
              126. [Label] Label (TEXT)
          127. [Divider] Divider (INSTANCE)
            128. [Divider] Divider (RECTANGLE)
        129. [Container] 02 Table Cell v1.1 (INSTANCE)
          130. [Container] .CellContent (INSTANCE)
            131. [Container] Content (FRAME)
              132. [Label] Label (TEXT)
          133. [Divider] Divider (INSTANCE)
            134. [Divider] Divider (RECTANGLE)
        135. [Container] 02 Table Cell v1.1 (INSTANCE)
          136. [Container] .CellContent (INSTANCE)
            137. [Container] Content (FRAME)
              138. [Label] Label (TEXT)
          139. [Divider] Divider (INSTANCE)
            140. [Divider] Divider (RECTANGLE)
        141. [Container] 02 Table Cell v1.1 (INSTANCE)
          142. [Container] .CellContent (INSTANCE)
            143. [Container] Content (FRAME)
              144. [Label] Label (TEXT)
          145. [Divider] Divider (INSTANCE)
            146. [Divider] Divider (RECTANGLE)
    147. [Container] 03 Table Row v1.1 (INSTANCE)
      148. [Container] Slot (SLOT)
        149. [Container] 02 Table Cell v1.1 (INSTANCE)
          150. [Container] .CellContent (INSTANCE)
            151. [Container] Content (FRAME)
              152. [Label] Label (TEXT)
          153. [Divider] Divider (INSTANCE)
            154. [Divider] Divider (RECTANGLE)
        155. [Container] 02 Table Cell v1.1 (INSTANCE)
          156. [Container] .CellContent (INSTANCE)
            157. [Container] Content (FRAME)
              158. [Label] Label (TEXT)
          159. [Divider] Divider (INSTANCE)
            160. [Divider] Divider (RECTANGLE)
        161. [Container] 02 Table Cell v1.1 (INSTANCE)
          162. [Container] .CellContent (INSTANCE)
            163. [Container] Content (FRAME)
              164. [Label] Label (TEXT)
          165. [Divider] Divider (INSTANCE)
            166. [Divider] Divider (RECTANGLE)
        167. [Container] 02 Table Cell v1.1 (INSTANCE)
          168. [Container] .CellContent (INSTANCE)
            169. [Container] Content (FRAME)
              170. [Label] Label (TEXT)
          171. [Divider] Divider (INSTANCE)
            172. [Divider] Divider (RECTANGLE)
        173. [Container] 02 Table Cell v1.1 (INSTANCE)
          174. [Container] .CellContent (INSTANCE)
            175. [Container] Content (FRAME)
              176. [Label] Label (TEXT)
          177. [Divider] Divider (INSTANCE)
            178. [Divider] Divider (RECTANGLE)
    179. [Container] 03 Table Row v1.1 (INSTANCE)
      180. [Container] Slot (SLOT)
        181. [Container] 02 Table Cell v1.1 (INSTANCE)
          182. [Container] .CellContent (INSTANCE)
            183. [Container] Content (FRAME)
              184. [Label] Label (TEXT)
          185. [Divider] Divider (INSTANCE)
            186. [Divider] Divider (RECTANGLE)
        187. [Container] 02 Table Cell v1.1 (INSTANCE)
          188. [Container] .CellContent (INSTANCE)
            189. [Container] Content (FRAME)
              190. [Label] Label (TEXT)
          191. [Divider] Divider (INSTANCE)
            192. [Divider] Divider (RECTANGLE)
        193. [Container] 02 Table Cell v1.1 (INSTANCE)
          194. [Container] .CellContent (INSTANCE)
            195. [Container] Content (FRAME)
              196. [Label] Label (TEXT)
          197. [Divider] Divider (INSTANCE)
            198. [Divider] Divider (RECTANGLE)
        199. [Container] 02 Table Cell v1.1 (INSTANCE)
          200. [Container] .CellContent (INSTANCE)
            201. [Container] Content (FRAME)
              202. [Label] Label (TEXT)
          203. [Divider] Divider (INSTANCE)
            204. [Divider] Divider (RECTANGLE)
        205. [Container] 02 Table Cell v1.1 (INSTANCE)
          206. [Container] .CellContent (INSTANCE)
            207. [Container] Content (FRAME)
              208. [Label] Label (TEXT)
          209. [Divider] Divider (INSTANCE)
            210. [Divider] Divider (RECTANGLE)
    211. [Container] 03 Table Row v1.1 (INSTANCE)
      212. [Container] Slot (SLOT)
        213. [Container] 02 Table Cell v1.1 (INSTANCE)
          214. [Container] .CellContent (INSTANCE)
            215. [Container] Content (FRAME)
              216. [Label] Label (TEXT)
          217. [Divider] Divider (INSTANCE)
            218. [Divider] Divider (RECTANGLE)
        219. [Container] 02 Table Cell v1.1 (INSTANCE)
          220. [Container] .CellContent (INSTANCE)
            221. [Container] Content (FRAME)
              222. [Label] Label (TEXT)
          223. [Divider] Divider (INSTANCE)
            224. [Divider] Divider (RECTANGLE)
        225. [Container] 02 Table Cell v1.1 (INSTANCE)
          226. [Container] .CellContent (INSTANCE)
            227. [Container] Content (FRAME)
              228. [Label] Label (TEXT)
          229. [Divider] Divider (INSTANCE)
            230. [Divider] Divider (RECTANGLE)
        231. [Container] 02 Table Cell v1.1 (INSTANCE)
          232. [Container] .CellContent (INSTANCE)
            233. [Container] Content (FRAME)
              234. [Label] Label (TEXT)
          235. [Divider] Divider (INSTANCE)
            236. [Divider] Divider (RECTANGLE)
        237. [Container] 02 Table Cell v1.1 (INSTANCE)
          238. [Container] .CellContent (INSTANCE)
            239. [Container] Content (FRAME)
              240. [Label] Label (TEXT)
          241. [Divider] Divider (INSTANCE)
            242. [Divider] Divider (RECTANGLE)
    243. [Container] 03 Table Row v1.1 (INSTANCE)
      244. [Container] Slot (SLOT)
        245. [Container] 02 Table Cell v1.1 (INSTANCE)
          246. [Container] .CellContent (INSTANCE)
            247. [Container] Content (FRAME)
              248. [Label] Label (TEXT)
          249. [Divider] Divider (INSTANCE)
            250. [Divider] Divider (RECTANGLE)
        251. [Container] 02 Table Cell v1.1 (INSTANCE)
          252. [Container] .CellContent (INSTANCE)
            253. [Container] Content (FRAME)
              254. [Label] Label (TEXT)
          255. [Divider] Divider (INSTANCE)
            256. [Divider] Divider (RECTANGLE)
        257. [Container] 02 Table Cell v1.1 (INSTANCE)
          258. [Container] .CellContent (INSTANCE)
            259. [Container] Content (FRAME)
              260. [Label] Label (TEXT)
          261. [Divider] Divider (INSTANCE)
            262. [Divider] Divider (RECTANGLE)
        263. [Container] 02 Table Cell v1.1 (INSTANCE)
          264. [Container] .CellContent (INSTANCE)
            265. [Container] Content (FRAME)
              266. [Label] Label (TEXT)
          267. [Divider] Divider (INSTANCE)
            268. [Divider] Divider (RECTANGLE)
        269. [Container] 02 Table Cell v1.1 (INSTANCE)
          270. [Container] .CellContent (INSTANCE)
            271. [Container] Content (FRAME)
              272. [Label] Label (TEXT)
          273. [Divider] Divider (INSTANCE)
            274. [Divider] Divider (RECTANGLE)
    275. [Container] 03 Table Row v1.1 (INSTANCE)
      276. [Container] Slot (SLOT)
        277. [Container] 02 Table Cell v1.1 (INSTANCE)
          278. [Container] .CellContent (INSTANCE)
            279. [Container] Content (FRAME)
              280. [Label] Label (TEXT)
          281. [Divider] Divider (INSTANCE)
            282. [Divider] Divider (RECTANGLE)
        283. [Container] 02 Table Cell v1.1 (INSTANCE)
          284. [Container] .CellContent (INSTANCE)
            285. [Container] Content (FRAME)
              286. [Label] Label (TEXT)
          287. [Divider] Divider (INSTANCE)
            288. [Divider] Divider (RECTANGLE)
        289. [Container] 02 Table Cell v1.1 (INSTANCE)
          290. [Container] .CellContent (INSTANCE)
            291. [Container] Content (FRAME)
              292. [Label] Label (TEXT)
          293. [Divider] Divider (INSTANCE)
            294. [Divider] Divider (RECTANGLE)
        295. [Container] 02 Table Cell v1.1 (INSTANCE)
          296. [Container] .CellContent (INSTANCE)
            297. [Container] Content (FRAME)
              298. [Label] Label (TEXT)
          299. [Divider] Divider (INSTANCE)
            300. [Divider] Divider (RECTANGLE)
        301. [Container] 02 Table Cell v1.1 (INSTANCE)
          302. [Container] .CellContent (INSTANCE)
            303. [Container] Content (FRAME)
              304. [Label] Label (TEXT)
          305. [Divider] Divider (INSTANCE)
            306. [Divider] Divider (RECTANGLE)
    307. [Container] 03 Table Row v1.1 (INSTANCE)
      308. [Container] Slot (SLOT)
        309. [Container] 02 Table Cell v1.1 (INSTANCE)
          310. [Container] .CellContent (INSTANCE)
            311. [Container] Content (FRAME)
              312. [Label] Label (TEXT)
          313. [Divider] Divider (INSTANCE)
            314. [Divider] Divider (RECTANGLE)
        315. [Container] 02 Table Cell v1.1 (INSTANCE)
          316. [Container] .CellContent (INSTANCE)
            317. [Container] Content (FRAME)
              318. [Label] Label (TEXT)
          319. [Divider] Divider (INSTANCE)
            320. [Divider] Divider (RECTANGLE)
        321. [Container] 02 Table Cell v1.1 (INSTANCE)
          322. [Container] .CellContent (INSTANCE)
            323. [Container] Content (FRAME)
              324. [Label] Label (TEXT)
          325. [Divider] Divider (INSTANCE)
            326. [Divider] Divider (RECTANGLE)
        327. [Container] 02 Table Cell v1.1 (INSTANCE)
          328. [Container] .CellContent (INSTANCE)
            329. [Container] Content (FRAME)
              330. [Label] Label (TEXT)
          331. [Divider] Divider (INSTANCE)
            332. [Divider] Divider (RECTANGLE)
        333. [Container] 02 Table Cell v1.1 (INSTANCE)
          334. [Container] .CellContent (INSTANCE)
            335. [Container] Content (FRAME)
              336. [Label] Label (TEXT)
          337. [Divider] Divider (INSTANCE)
            338. [Divider] Divider (RECTANGLE)
    339. [Container] 03 Table Row v1.1 (INSTANCE)
      340. [Container] Slot (SLOT)
        341. [Container] 02 Table Cell v1.1 (INSTANCE)
          342. [Container] .CellContent (INSTANCE)
            343. [Container] Content (FRAME)
              344. [Label] Label (TEXT)
          345. [Divider] Divider (INSTANCE)
            346. [Divider] Divider (RECTANGLE)
        347. [Container] 02 Table Cell v1.1 (INSTANCE)
          348. [Container] .CellContent (INSTANCE)
            349. [Container] Content (FRAME)
              350. [Label] Label (TEXT)
          351. [Divider] Divider (INSTANCE)
            352. [Divider] Divider (RECTANGLE)
        353. [Container] 02 Table Cell v1.1 (INSTANCE)
          354. [Container] .CellContent (INSTANCE)
            355. [Container] Content (FRAME)
              356. [Label] Label (TEXT)
          357. [Divider] Divider (INSTANCE)
            358. [Divider] Divider (RECTANGLE)
        359. [Container] 02 Table Cell v1.1 (INSTANCE)
          360. [Container] .CellContent (INSTANCE)
            361. [Container] Content (FRAME)
              362. [Label] Label (TEXT)
          363. [Divider] Divider (INSTANCE)
            364. [Divider] Divider (RECTANGLE)
        365. [Container] 02 Table Cell v1.1 (INSTANCE)
          366. [Container] .CellContent (INSTANCE)
            367. [Container] Content (FRAME)
              368. [Label] Label (TEXT)
          369. [Divider] Divider (INSTANCE)
            370. [Divider] Divider (RECTANGLE)
    371. [Container] 03 Table Row v1.1 (INSTANCE)
      372. [Container] Slot (SLOT)
        373. [Container] 02 Table Cell v1.1 (INSTANCE)
          374. [Container] .CellContent (INSTANCE)
            375. [Container] Content (FRAME)
              376. [Label] Label (TEXT)
          377. [Divider] Divider (INSTANCE)
            378. [Divider] Divider (RECTANGLE)
        379. [Container] 02 Table Cell v1.1 (INSTANCE)
          380. [Container] .CellContent (INSTANCE)
            381. [Container] Content (FRAME)
              382. [Label] Label (TEXT)
          383. [Divider] Divider (INSTANCE)
            384. [Divider] Divider (RECTANGLE)
        385. [Container] 02 Table Cell v1.1 (INSTANCE)
          386. [Container] .CellContent (INSTANCE)
            387. [Container] Content (FRAME)
              388. [Label] Label (TEXT)
          389. [Divider] Divider (INSTANCE)
            390. [Divider] Divider (RECTANGLE)
        391. [Container] 02 Table Cell v1.1 (INSTANCE)
          392. [Container] .CellContent (INSTANCE)
            393. [Container] Content (FRAME)
              394. [Label] Label (TEXT)
          395. [Divider] Divider (INSTANCE)
            396. [Divider] Divider (RECTANGLE)
        397. [Container] 02 Table Cell v1.1 (INSTANCE)
          398. [Container] .CellContent (INSTANCE)
            399. [Container] Content (FRAME)
              400. [Label] Label (TEXT)
          401. [Divider] Divider (INSTANCE)
            402. [Divider] Divider (RECTANGLE)
    403. [Container] 03 Table Row v1.1 (INSTANCE)
      404. [Container] Slot (SLOT)
        405. [Container] 02 Table Cell v1.1 (INSTANCE)
          406. [Container] .CellContent (INSTANCE)
            407. [Container] Content (FRAME)
              408. [Label] Label (TEXT)
          409. [Divider] Divider (INSTANCE)
            410. [Divider] Divider (RECTANGLE)
        411. [Container] 02 Table Cell v1.1 (INSTANCE)
          412. [Container] .CellContent (INSTANCE)
            413. [Container] Content (FRAME)
              414. [Label] Label (TEXT)
          415. [Divider] Divider (INSTANCE)
            416. [Divider] Divider (RECTANGLE)
        417. [Container] 02 Table Cell v1.1 (INSTANCE)
          418. [Container] .CellContent (INSTANCE)
            419. [Container] Content (FRAME)
              420. [Label] Label (TEXT)
          421. [Divider] Divider (INSTANCE)
            422. [Divider] Divider (RECTANGLE)
        423. [Container] 02 Table Cell v1.1 (INSTANCE)
          424. [Container] .CellContent (INSTANCE)
            425. [Container] Content (FRAME)
              426. [Label] Label (TEXT)
          427. [Divider] Divider (INSTANCE)
            428. [Divider] Divider (RECTANGLE)
        429. [Container] 02 Table Cell v1.1 (INSTANCE)
          430. [Container] .CellContent (INSTANCE)
            431. [Container] Content (FRAME)
              432. [Label] Label (TEXT)
          433. [Divider] Divider (INSTANCE)
            434. [Divider] Divider (RECTANGLE)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Orientations=Rows Based, Size=Default | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| Orientations=Rows Based, Size=Default | itemSpacing | `10px` | `—` | `—` |
| 03 Table Row v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 01 Table Header v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 01 Table Header v1.1 | paddingTop | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 01 Table Header v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 01 Table Header v1.1 | paddingBottom | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 01 Table Header v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 01 Table Header v1.1 | itemSpacing | `24px` | `padding.6` | `var(--ach-padding-6)` |
| .Header Content | itemSpacing | `16px` | `—` | `—` |
| Wrapper | itemSpacing | `10px` | `—` | `—` |
| .Resize-Handle | itemSpacing | `10px` | `—` | `—` |
| shape | fill | `#181D1F` | `borders.borderColor` | `var(--ach-borders-borderColor)` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Icons/ui-actions/drag-indicator | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `icon.ach-color-icon-subtle` | `var(--ach-icon-ach-color-icon-subtle)` |
| 01 Checkbox | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Checkbox | itemSpacing | `10px` | `—` | `—` |
| Background | fill | `#FFFFFF` | `checkbox.default.background` | `var(--ach-checkbox-default-background)` |
| Background | stroke | `#BDBDBD` | `checkbox.default.border` | `var(--ach-checkbox-default-border)` |
| Background | cornerRadius | `4px` | `borderRadius.xs` | `var(--ach-borderRadius-xs)` |
| Label | fill | `#262626` | `checkbox.default.text` | `var(--ach-checkbox-default-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Label | fill | `#525252` | `table.headerText` | `var(--ach-table-headerText)` |
| Label | fontSize | `14px` | `—` | `—` |
| .Sorting Control | fill | `#FFFFFF` | `—` | `—` |
| Icons/ui-actions/arrow-upward | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `icon.ach-color-icon-subtle` | `var(--ach-icon-ach-color-icon-subtle)` |
| .Resize-Handle | itemSpacing | `10px` | `—` | `—` |
| shape | fill | `#181D1F` | `borders.borderColor` | `var(--ach-borders-borderColor)` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 01 Table Header v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 01 Table Header v1.1 | paddingTop | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 01 Table Header v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 01 Table Header v1.1 | paddingBottom | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 01 Table Header v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 01 Table Header v1.1 | itemSpacing | `24px` | `padding.6` | `var(--ach-padding-6)` |
| .Header Content | itemSpacing | `16px` | `—` | `—` |
| Wrapper | itemSpacing | `10px` | `—` | `—` |
| .Resize-Handle | itemSpacing | `10px` | `—` | `—` |
| shape | fill | `#181D1F` | `borders.borderColor` | `var(--ach-borders-borderColor)` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Icons/ui-actions/drag-indicator | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `icon.ach-color-icon-subtle` | `var(--ach-icon-ach-color-icon-subtle)` |
| 01 Checkbox | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Checkbox | itemSpacing | `10px` | `—` | `—` |
| Background | fill | `#FFFFFF` | `checkbox.default.background` | `var(--ach-checkbox-default-background)` |
| Background | stroke | `#BDBDBD` | `checkbox.default.border` | `var(--ach-checkbox-default-border)` |
| Background | cornerRadius | `4px` | `borderRadius.xs` | `var(--ach-borderRadius-xs)` |
| Label | fill | `#262626` | `checkbox.default.text` | `var(--ach-checkbox-default-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Label | fill | `#525252` | `table.headerText` | `var(--ach-table-headerText)` |
| Label | fontSize | `14px` | `—` | `—` |
| .Sorting Control | fill | `#FFFFFF` | `—` | `—` |
| Icons/ui-actions/arrow-upward | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `icon.ach-color-icon-subtle` | `var(--ach-icon-ach-color-icon-subtle)` |
| .Resize-Handle | itemSpacing | `10px` | `—` | `—` |
| shape | fill | `#181D1F` | `borders.borderColor` | `var(--ach-borders-borderColor)` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 01 Table Header v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 01 Table Header v1.1 | paddingTop | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 01 Table Header v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 01 Table Header v1.1 | paddingBottom | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 01 Table Header v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 01 Table Header v1.1 | itemSpacing | `24px` | `padding.6` | `var(--ach-padding-6)` |
| .Header Content | itemSpacing | `16px` | `—` | `—` |
| Wrapper | itemSpacing | `10px` | `—` | `—` |
| .Resize-Handle | itemSpacing | `10px` | `—` | `—` |
| shape | fill | `#181D1F` | `borders.borderColor` | `var(--ach-borders-borderColor)` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Icons/ui-actions/drag-indicator | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `icon.ach-color-icon-subtle` | `var(--ach-icon-ach-color-icon-subtle)` |
| 01 Checkbox | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Checkbox | itemSpacing | `10px` | `—` | `—` |
| Background | fill | `#FFFFFF` | `checkbox.default.background` | `var(--ach-checkbox-default-background)` |
| Background | stroke | `#BDBDBD` | `checkbox.default.border` | `var(--ach-checkbox-default-border)` |
| Background | cornerRadius | `4px` | `borderRadius.xs` | `var(--ach-borderRadius-xs)` |
| Label | fill | `#262626` | `checkbox.default.text` | `var(--ach-checkbox-default-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Label | fill | `#525252` | `table.headerText` | `var(--ach-table-headerText)` |
| Label | fontSize | `14px` | `—` | `—` |
| .Sorting Control | fill | `#FFFFFF` | `—` | `—` |
| Icons/ui-actions/arrow-upward | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `icon.ach-color-icon-subtle` | `var(--ach-icon-ach-color-icon-subtle)` |
| .Resize-Handle | itemSpacing | `10px` | `—` | `—` |
| shape | fill | `#181D1F` | `borders.borderColor` | `var(--ach-borders-borderColor)` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 01 Table Header v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 01 Table Header v1.1 | paddingTop | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 01 Table Header v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 01 Table Header v1.1 | paddingBottom | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 01 Table Header v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 01 Table Header v1.1 | itemSpacing | `24px` | `padding.6` | `var(--ach-padding-6)` |
| .Header Content | itemSpacing | `16px` | `—` | `—` |
| Wrapper | itemSpacing | `10px` | `—` | `—` |
| .Resize-Handle | itemSpacing | `10px` | `—` | `—` |
| shape | fill | `#181D1F` | `borders.borderColor` | `var(--ach-borders-borderColor)` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Icons/ui-actions/drag-indicator | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `icon.ach-color-icon-subtle` | `var(--ach-icon-ach-color-icon-subtle)` |
| 01 Checkbox | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Checkbox | itemSpacing | `10px` | `—` | `—` |
| Background | fill | `#FFFFFF` | `checkbox.default.background` | `var(--ach-checkbox-default-background)` |
| Background | stroke | `#BDBDBD` | `checkbox.default.border` | `var(--ach-checkbox-default-border)` |
| Background | cornerRadius | `4px` | `borderRadius.xs` | `var(--ach-borderRadius-xs)` |
| Label | fill | `#262626` | `checkbox.default.text` | `var(--ach-checkbox-default-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Label | fill | `#525252` | `table.headerText` | `var(--ach-table-headerText)` |
| Label | fontSize | `14px` | `—` | `—` |
| .Sorting Control | fill | `#FFFFFF` | `—` | `—` |
| Icons/ui-actions/arrow-upward | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `icon.ach-color-icon-subtle` | `var(--ach-icon-ach-color-icon-subtle)` |
| .Resize-Handle | itemSpacing | `10px` | `—` | `—` |
| shape | fill | `#181D1F` | `borders.borderColor` | `var(--ach-borders-borderColor)` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 01 Table Header v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 01 Table Header v1.1 | paddingTop | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 01 Table Header v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 01 Table Header v1.1 | paddingBottom | `12px` | `padding.3` | `var(--ach-padding-3)` |
| 01 Table Header v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 01 Table Header v1.1 | itemSpacing | `24px` | `padding.6` | `var(--ach-padding-6)` |
| .Header Content | itemSpacing | `16px` | `—` | `—` |
| Wrapper | itemSpacing | `10px` | `—` | `—` |
| .Resize-Handle | itemSpacing | `10px` | `—` | `—` |
| shape | fill | `#181D1F` | `borders.borderColor` | `var(--ach-borders-borderColor)` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Icons/ui-actions/drag-indicator | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `icon.ach-color-icon-subtle` | `var(--ach-icon-ach-color-icon-subtle)` |
| 01 Checkbox | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Checkbox | itemSpacing | `10px` | `—` | `—` |
| Background | fill | `#FFFFFF` | `checkbox.default.background` | `var(--ach-checkbox-default-background)` |
| Background | stroke | `#BDBDBD` | `checkbox.default.border` | `var(--ach-checkbox-default-border)` |
| Background | cornerRadius | `4px` | `borderRadius.xs` | `var(--ach-borderRadius-xs)` |
| Label | fill | `#262626` | `checkbox.default.text` | `var(--ach-checkbox-default-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Label | fill | `#525252` | `table.headerText` | `var(--ach-table-headerText)` |
| Label | fontSize | `14px` | `—` | `—` |
| .Sorting Control | fill | `#FFFFFF` | `—` | `—` |
| Icons/ui-actions/arrow-upward | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `icon.ach-color-icon-subtle` | `var(--ach-icon-ach-color-icon-subtle)` |
| .Resize-Handle | itemSpacing | `10px` | `—` | `—` |
| shape | fill | `#181D1F` | `borders.borderColor` | `var(--ach-borders-borderColor)` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 03 Table Row v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 03 Table Row v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 03 Table Row v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 03 Table Row v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 03 Table Row v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 03 Table Row v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 03 Table Row v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 03 Table Row v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 03 Table Row v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 03 Table Row v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
| Divider | stroke | `#DCDCDC` | `divider.default` | `var(--ach-divider-default)` |
| 02 Table Cell v1.1 | fill | `#FFFFFF` | `bg.ach-color-bg-surface` | `var(--ach-bg-ach-color-bg-surface)` |
| 02 Table Cell v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Table Cell v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 02 Table Cell v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .CellContent | itemSpacing | `16px` | `—` | `—` |
| Content | itemSpacing | `16px` | `—` | `—` |
| Label | fill | `#262626` | `table.rowText` | `var(--ach-table-rowText)` |
| Label | fontSize | `14px` | `—` | `—` |
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
