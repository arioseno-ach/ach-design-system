---
id: badge-solid
name: BadgeSolid
category: primitive
figma_component_name: "Badge Solid"
figma_url: "https://www.figma.com/design//?node-id=1476-1535"
status: draft
tokens_used:
  - badge.solid.primary.background
  - borderRadius.sm
  - 3xs
  - xs
  - 2xs
  - badge.solid.primary.icon
  - badge.solid.primary.text
---

# BadgeSolid

> A small label with a solid fill used to highlight status, category, or count. Solid variant.
AKA: Tag, Label, Chip, Pill, Status Badge, Status Label

## Code contract

```typescript
interface BadgeSolidProps {
  /** Text content: Label */
  Label?: React.ReactNode;
  /** Toggle: Show left icon */
  Show left icon?: boolean;
  /** Toggle: Show right icon */
  Show right icon?: boolean;
  /** Slot: ⮑ Icon left */
  ⮑ Icon left?: React.ReactNode;
  /** Slot: ⮑ Icon right */
  ⮑ Icon right?: React.ReactNode;
  /** Visual variant: Style */
  Style?: 'Solid' | 'Soft';
  /** Visual variant: Color */
  Color?: 'Primary' | 'Secondary' | 'Info' | 'Warning' | 'Error' | 'Success';
  /** Visual variant: Size */
  Size?: 'Small' | 'Medium' | 'Large';
  /** Visual variant: Roundness */
  Roundness?: 'Default' | 'Round';
  /** Visual variant: State */
  State?: 'Default' | 'Hover';
  children?: React.ReactNode;
  className?: string;
}
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Style | `Solid`, `Soft` | `Solid` | Visual variant: Style |
| Color | `Primary`, `Secondary`, `Info`, `Warning`, `Error`, `Success` | `Primary` | Visual variant: Color |
| Size | `Small`, `Medium`, `Large` | `Small` | Visual variant: Size |
| Roundness | `Default`, `Round` | `Default` | Visual variant: Roundness |
| State | `Default`, `Hover` | `Default` | Visual variant: State |

## Anatomy

```
1. [Root] Style=Solid, Color=Primary, Size=Small, Roundness=Default, State=Default (COMPONENT)
  2. [Icon] Left icon (INSTANCE)
    3. [Element] Vector (VECTOR)
  4. [Label] Label (TEXT)
  5. [Icon] Right icon (INSTANCE)
    6. [Element] Vector (VECTOR)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Style=Solid, Color=Primary, Size=Small, Roundness=Default, State=Default | fill | `#171717` | `badge.solid.primary.background` | `var(--ach-badge-solid-primary-background)` |
| Style=Solid, Color=Primary, Size=Small, Roundness=Default, State=Default | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Style=Solid, Color=Primary, Size=Small, Roundness=Default, State=Default | paddingTop | `2px` | `3xs` | `var(--ach-3xs)` |
| Style=Solid, Color=Primary, Size=Small, Roundness=Default, State=Default | paddingRight | `8px` | `xs` | `var(--ach-xs)` |
| Style=Solid, Color=Primary, Size=Small, Roundness=Default, State=Default | paddingBottom | `2px` | `3xs` | `var(--ach-3xs)` |
| Style=Solid, Color=Primary, Size=Small, Roundness=Default, State=Default | paddingLeft | `8px` | `xs` | `var(--ach-xs)` |
| Style=Solid, Color=Primary, Size=Small, Roundness=Default, State=Default | itemSpacing | `4px` | `2xs` | `var(--ach-2xs)` |
| Left icon | fill | `#FFFFFF` | `badge.solid.primary.icon` | `var(--ach-badge-solid-primary-icon)` |
| Vector | fill | `#FFFFFF` | `badge.solid.primary.icon` | `var(--ach-badge-solid-primary-icon)` |
| Label | fill | `#FFFFFF` | `badge.solid.primary.text` | `var(--ach-badge-solid-primary-text)` |
| Label | fontSize | `12px` | `—` | `—` |
| Right icon | fill | `#FFFFFF` | `badge.solid.primary.icon` | `var(--ach-badge-solid-primary-icon)` |
| Vector | fill | `#FFFFFF` | `badge.solid.primary.icon` | `var(--ach-badge-solid-primary-icon)` |

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
id: badge-outline
name: BadgeOutline
category: primitive
figma_component_name: "Badge Outline"
figma_url: "https://www.figma.com/design//?node-id=1476-39401"
status: draft
tokens_used:
  - badge.outline.primary.background
  - badge.soft.primary.border
  - borderRadius.sm
  - 3xs
  - xs
  - 2xs
  - badge.soft.primary.icon
  - badge.soft.primary.text
---

# BadgeOutline

> A small label with an outlined stroke used to highlight status, category, or count. Outlined variant.
AKA: Tag, Label, Chip, Pill, Outline Badge, Status Tag

## Code contract

```typescript
interface BadgeOutlineProps {
  /** Text content: Label */
  Label?: React.ReactNode;
  /** Toggle: Show left icon */
  Show left icon?: boolean;
  /** Toggle: Show right icon */
  Show right icon?: boolean;
  /** Slot: ⮑ Icon left */
  ⮑ Icon left?: React.ReactNode;
  /** Slot: ⮑ Icon right */
  ⮑ Icon right?: React.ReactNode;
  /** Visual variant: Color */
  Color?: 'Primary' | 'Secondary' | 'Info' | 'Warning' | 'Error' | 'Success';
  /** Visual variant: Size */
  Size?: 'Small' | 'Medium' | 'Large';
  /** Visual variant: Roundness */
  Roundness?: 'Default' | 'Round';
  /** Visual variant: State */
  State?: 'Default' | 'Hover';
  children?: React.ReactNode;
  className?: string;
}
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Color | `Primary`, `Secondary`, `Info`, `Warning`, `Error`, `Success` | `Primary` | Visual variant: Color |
| Size | `Small`, `Medium`, `Large` | `Small` | Visual variant: Size |
| Roundness | `Default`, `Round` | `Default` | Visual variant: Roundness |
| State | `Default`, `Hover` | `Default` | Visual variant: State |

## Anatomy

```
1. [Root] Color=Primary, Size=Small, Roundness=Default, State=Default (COMPONENT)
  2. [Icon] Left icon (INSTANCE)
    3. [Element] Vector (VECTOR)
  4. [Label] Label (TEXT)
  5. [Icon] Right icon (INSTANCE)
    6. [Element] Vector (VECTOR)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Color=Primary, Size=Small, Roundness=Default, State=Default | fill | `#FFFFFF` | `badge.outline.primary.background` | `var(--ach-badge-outline-primary-background)` |
| Color=Primary, Size=Small, Roundness=Default, State=Default | stroke | `#BDBDBD` | `badge.soft.primary.border` | `var(--ach-badge-soft-primary-border)` |
| Color=Primary, Size=Small, Roundness=Default, State=Default | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Color=Primary, Size=Small, Roundness=Default, State=Default | paddingTop | `2px` | `3xs` | `var(--ach-3xs)` |
| Color=Primary, Size=Small, Roundness=Default, State=Default | paddingRight | `8px` | `xs` | `var(--ach-xs)` |
| Color=Primary, Size=Small, Roundness=Default, State=Default | paddingBottom | `2px` | `3xs` | `var(--ach-3xs)` |
| Color=Primary, Size=Small, Roundness=Default, State=Default | paddingLeft | `8px` | `xs` | `var(--ach-xs)` |
| Color=Primary, Size=Small, Roundness=Default, State=Default | itemSpacing | `4px` | `2xs` | `var(--ach-2xs)` |
| Left icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `badge.soft.primary.icon` | `var(--ach-badge-soft-primary-icon)` |
| Label | fill | `#262626` | `badge.soft.primary.text` | `var(--ach-badge-soft-primary-text)` |
| Label | fontSize | `12px` | `—` | `—` |
| Right icon | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `badge.soft.primary.icon` | `var(--ach-badge-soft-primary-icon)` |

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
id: badge-number
name: BadgeNumber
category: primitive
figma_component_name: "Badge Number"
figma_url: "https://www.figma.com/design//?node-id=1476-39438"
status: draft
tokens_used:
  - badge.solid.primary.background
  - borderRadius.infinite
  - badge.solid.primary.text
---

# BadgeNumber

> A small circular badge displaying a numeric count, typically overlaid on icons or elements.
AKA: Count Badge, Notification Count, Counter, Number Indicator, Unread Count

## Code contract

```typescript
interface BadgeNumberProps {
  /** Text content: Count */
  Count?: React.ReactNode;
  /** Visual variant: Color */
  Color?: 'Primary' | 'Secondary' | 'Info' | 'Warning' | 'Error' | 'Success';
  /** Visual variant: Size */
  Size?: 'Small' | 'Medium' | 'Large';
  children?: React.ReactNode;
  className?: string;
}
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Color | `Primary`, `Secondary`, `Info`, `Warning`, `Error`, `Success` | `Primary` | Visual variant: Color |
| Size | `Small`, `Medium`, `Large` | `Small` | Visual variant: Size |

## Anatomy

```
1. [Root] Color=Primary, Size=Small (COMPONENT)
  2. [Label] 1 (TEXT)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Color=Primary, Size=Small | fill | `#171717` | `badge.solid.primary.background` | `var(--ach-badge-solid-primary-background)` |
| Color=Primary, Size=Small | cornerRadius | `9999px` | `borderRadius.infinite` | `var(--ach-borderRadius-infinite)` |
| Color=Primary, Size=Small | paddingRight | `4px` | `—` | `—` |
| Color=Primary, Size=Small | paddingLeft | `4px` | `—` | `—` |
| 1 | fill | `#FFFFFF` | `badge.solid.primary.text` | `var(--ach-badge-solid-primary-text)` |
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


---

---
id: badge-dot
name: BadgeDot
category: primitive
figma_component_name: "Badge Dot"
figma_url: "https://www.figma.com/design//?node-id=1476-39457"
status: draft
tokens_used:
  - badge.solid.primary.background
  - borderRadius.infinite
---

# BadgeDot

> A small dot indicator used to signal status or draw attention without displaying a number.
AKA: Status Dot, Indicator Dot, Notification Dot, Presence Indicator, Online Dot

## Code contract

```typescript
interface BadgeDotProps {
  /** Visual variant: Color */
  Color?: 'Primary' | 'Secondary' | 'Info' | 'Warning' | 'Error' | 'Success';
  /** Visual variant: Size */
  Size?: 'Small' | 'Medium' | 'Large';
  children?: React.ReactNode;
  className?: string;
}
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Color | `Primary`, `Secondary`, `Info`, `Warning`, `Error`, `Success` | `Primary` | Visual variant: Color |
| Size | `Small`, `Medium`, `Large` | `Small` | Visual variant: Size |

## Anatomy

```
1. [Root] Color=Primary, Size=Small (COMPONENT)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Color=Primary, Size=Small | fill | `#171717` | `badge.solid.primary.background` | `var(--ach-badge-solid-primary-background)` |
| Color=Primary, Size=Small | cornerRadius | `9999px` | `borderRadius.infinite` | `var(--ach-borderRadius-infinite)` |

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
