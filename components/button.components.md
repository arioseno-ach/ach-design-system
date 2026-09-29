---
id: button-outlined-v1.1
name: ButtonOutlinedV1.1
category: primitive
figma_component_name: "Button Outlined v1.1"
figma_url: "https://www.figma.com/design//?node-id=1179-16323"
status: draft
tokens_used:
  - button.outlined.primary.border
  - borderRadius.infinite
  - padding.2
  - padding.4
  - button.outlined.primary.text
---

# ButtonOutlinedV1.1

> An interactive element that triggers an action when clicked or tapped. Buttons communicate the action that will occur and allow users to interact with the interface.

## Code contract

```typescript
interface ButtonOutlinedV1.1Props {
  /** Toggle: Show left icon */
  Show left icon?: boolean;
  /** Toggle: Show right icon */
  Show right icon?: boolean;
  /** Slot: ⮑ Left icon */
  ⮑ Left icon?: React.ReactNode;
  /** Slot: ⮑ Right icon */
  ⮑ Right icon?: React.ReactNode;
  /** Text content: Label */
  Label?: React.ReactNode;
  /** Visual variant: Color */
  Color?: 'Primary' | 'Success' | 'Warning' | 'Error' | 'Brand' | 'Neutral' | 'Inverse';
  /** Visual variant: Size */
  Size?: 'Default' | 'Small' | 'Mini' | 'Large' | 'Extra Large';
  /** Visual variant: State */
  State?: 'Default' | 'Hover & Active' | 'Disabled';
  children?: React.ReactNode;
  className?: string;
}
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Color | `Primary`, `Success`, `Warning`, `Error`, `Brand`, `Neutral`, `Inverse` | `Primary` | Visual variant: Color |
| Size | `Default`, `Small`, `Mini`, `Large`, `Extra Large` | `Default` | Visual variant: Size |
| State | `Default`, `Hover & Active`, `Disabled` | `Default` | Visual variant: State |

## Anatomy

```
1. [Root] Color=Primary, Size=Default, State=Default (COMPONENT)
  2. [Icon] Left icon (INSTANCE)
    3. [Element] Vector (VECTOR)
  4. [Label] Button (TEXT)
  5. [Icon] Right icon (INSTANCE)
    6. [Element] Vector (VECTOR)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Color=Primary, Size=Default, State=Default | stroke | `#DCDCDC` | `button.outlined.primary.border` | `var(--ach-button-outlined-primary-border)` |
| Color=Primary, Size=Default, State=Default | cornerRadius | `9999px` | `borderRadius.infinite` | `var(--ach-borderRadius-infinite)` |
| Color=Primary, Size=Default, State=Default | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Color=Primary, Size=Default, State=Default | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Color=Primary, Size=Default, State=Default | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Color=Primary, Size=Default, State=Default | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Color=Primary, Size=Default, State=Default | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Left icon | fill | `#262626` | `button.outlined.primary.text` | `var(--ach-button-outlined-primary-text)` |
| Vector | fill | `#262626` | `button.outlined.primary.text` | `var(--ach-button-outlined-primary-text)` |
| Button | fill | `#262626` | `button.outlined.primary.text` | `var(--ach-button-outlined-primary-text)` |
| Button | fontSize | `14px` | `—` | `—` |
| Right icon | fill | `#262626` | `button.outlined.primary.text` | `var(--ach-button-outlined-primary-text)` |
| Vector | fill | `#262626` | `button.outlined.primary.text` | `var(--ach-button-outlined-primary-text)` |

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
id: button-icon-v1.1
name: ButtonIconV1.1
category: primitive
figma_component_name: "Button Icon v1.1"
figma_url: "https://www.figma.com/design//?node-id=1179-16678"
status: draft
tokens_used:
  - button.icon.primary.bg
  - borderRadius.infinite
  - padding.2
  - padding.3
  - button.icon.primary.icon
---

# ButtonIconV1.1

> An interactive element that triggers an action when clicked or tapped. Buttons communicate the action that will occur and allow users to interact with the interface.

## Code contract

```typescript
interface ButtonIconV1.1Props {
  /** Slot: Icon */
  Icon?: React.ReactNode;
  /** Visual variant: Color */
  Color?: 'Primary' | 'Success' | 'Warning' | 'Error' | 'Brand' | 'Neutral' | 'Inverse';
  /** Visual variant: Size */
  Size?: 'Small' | 'Default' | 'Large' | 'Mini' | 'Extra Large';
  /** Visual variant: State */
  State?: 'Default' | 'Hover & Active' | 'Disabled';
  children?: React.ReactNode;
  className?: string;
}
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Color | `Primary`, `Success`, `Warning`, `Error`, `Brand`, `Neutral`, `Inverse` | `Primary` | Visual variant: Color |
| Size | `Small`, `Default`, `Large`, `Mini`, `Extra Large` | `Default` | Visual variant: Size |
| State | `Default`, `Hover & Active`, `Disabled` | `Default` | Visual variant: State |

## Anatomy

```
1. [Root] Color=Primary, Size=Default, State=Default (COMPONENT)
  2. [Icon] Icons (FRAME)
    3. [Icon] Icons/business-payments/shopping-cart (INSTANCE)
      4. [Element] Vector (VECTOR)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Color=Primary, Size=Default, State=Default | fill | `#171717` | `button.icon.primary.bg` | `var(--ach-button-icon-primary-bg)` |
| Color=Primary, Size=Default, State=Default | cornerRadius | `9999px` | `borderRadius.infinite` | `var(--ach-borderRadius-infinite)` |
| Color=Primary, Size=Default, State=Default | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Color=Primary, Size=Default, State=Default | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Color=Primary, Size=Default, State=Default | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Color=Primary, Size=Default, State=Default | paddingLeft | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Color=Primary, Size=Default, State=Default | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Icons | itemSpacing | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Icons/business-payments/shopping-cart | fill | `#FFFFFF` | `button.icon.primary.icon` | `var(--ach-button-icon-primary-icon)` |
| Vector | fill | `#FFFFFF` | `button.icon.primary.icon` | `var(--ach-button-icon-primary-icon)` |

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
id: button-link-v1.1
name: ButtonLinkV1.1
category: primitive
figma_component_name: "Button Link v1.1"
figma_url: "https://www.figma.com/design//?node-id=1179-17039"
status: draft
tokens_used:
  - borderRadius.infinite
  - padding.2
  - padding.4
  - button.link.primary.text
---

# ButtonLinkV1.1

> An interactive element that triggers an action when clicked or tapped. Buttons communicate the action that will occur and allow users to interact with the interface.

## Code contract

```typescript
interface ButtonLinkV1.1Props {
  /** Toggle: Show left icon */
  Show left icon?: boolean;
  /** Toggle: Show right icon */
  Show right icon?: boolean;
  /** Slot: ⮑ Left icon */
  ⮑ Left icon?: React.ReactNode;
  /** Slot: ⮑ Right icon */
  ⮑ Right icon?: React.ReactNode;
  /** Text content: Label */
  Label?: React.ReactNode;
  /** Visual variant: Color */
  Color?: 'Primary' | 'Success' | 'Warning' | 'Error' | 'Brand' | 'Neutral' | 'Inverse';
  /** Visual variant: Size */
  Size?: 'Default' | 'Small' | 'Mini' | 'Large' | 'Extra Large';
  /** Visual variant: State */
  State?: 'Default' | 'Hover & Active' | 'Disabled';
  children?: React.ReactNode;
  className?: string;
}
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Color | `Primary`, `Success`, `Warning`, `Error`, `Brand`, `Neutral`, `Inverse` | `Primary` | Visual variant: Color |
| Size | `Default`, `Small`, `Mini`, `Large`, `Extra Large` | `Default` | Visual variant: Size |
| State | `Default`, `Hover & Active`, `Disabled` | `Default` | Visual variant: State |

## Anatomy

```
1. [Root] Color=Primary, Size=Default, State=Default (COMPONENT)
  2. [Icon] Left icon (INSTANCE)
    3. [Element] Vector (VECTOR)
  4. [Label] Button (TEXT)
  5. [Icon] Right icon (INSTANCE)
    6. [Element] Vector (VECTOR)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Color=Primary, Size=Default, State=Default | cornerRadius | `9999px` | `borderRadius.infinite` | `var(--ach-borderRadius-infinite)` |
| Color=Primary, Size=Default, State=Default | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Color=Primary, Size=Default, State=Default | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Color=Primary, Size=Default, State=Default | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Color=Primary, Size=Default, State=Default | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Color=Primary, Size=Default, State=Default | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Left icon | fill | `#262626` | `button.link.primary.text` | `var(--ach-button-link-primary-text)` |
| Vector | fill | `#262626` | `button.link.primary.text` | `var(--ach-button-link-primary-text)` |
| Button | fill | `#262626` | `button.link.primary.text` | `var(--ach-button-link-primary-text)` |
| Button | fontSize | `14px` | `—` | `—` |
| Right icon | fill | `#262626` | `button.link.primary.text` | `var(--ach-button-link-primary-text)` |
| Vector | fill | `#262626` | `button.link.primary.text` | `var(--ach-button-link-primary-text)` |

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
id: button-fab-v1.1
name: ButtonFABV1.1
category: primitive
figma_component_name: "Button FAB v1.1"
figma_url: "https://www.figma.com/design//?node-id=1179-17310"
status: draft
tokens_used:
  - button.fab.primary.bg
  - borderRadius.infinite
  - padding.4
  - padding.2
  - padding.3
  - button.fab.primary.icon
---

# ButtonFABV1.1

> An interactive element that triggers an action when clicked or tapped. Buttons communicate the action that will occur and allow users to interact with the interface.

## Code contract

```typescript
interface ButtonFABV1.1Props {
  /** Slot: Icon */
  Icon?: React.ReactNode;
  /** Visual variant: Color */
  Color?: 'Primary' | 'Success' | 'Warning' | 'Error' | 'Brand' | 'Neutral' | 'Inverse';
  /** Visual variant: Size */
  Size?: 'Small' | 'Default' | 'Large';
  /** Visual variant: State */
  State?: 'Default' | 'Hover & Active' | 'Disabled';
  children?: React.ReactNode;
  className?: string;
}
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Color | `Primary`, `Success`, `Warning`, `Error`, `Brand`, `Neutral`, `Inverse` | `Primary` | Visual variant: Color |
| Size | `Small`, `Default`, `Large` | `Default` | Visual variant: Size |
| State | `Default`, `Hover & Active`, `Disabled` | `Default` | Visual variant: State |

## Anatomy

```
1. [Root] Color=Primary, Size=Default, State=Default (COMPONENT)
  2. [Icon] Icons (FRAME)
    3. [Icon] Icons/business-payments/shopping-cart (INSTANCE)
      4. [Element] Vector (VECTOR)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Color=Primary, Size=Default, State=Default | fill | `#171717` | `button.fab.primary.bg` | `var(--ach-button-fab-primary-bg)` |
| Color=Primary, Size=Default, State=Default | cornerRadius | `9999px` | `borderRadius.infinite` | `var(--ach-borderRadius-infinite)` |
| Color=Primary, Size=Default, State=Default | paddingTop | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Color=Primary, Size=Default, State=Default | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Color=Primary, Size=Default, State=Default | paddingBottom | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Color=Primary, Size=Default, State=Default | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Color=Primary, Size=Default, State=Default | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Icons | itemSpacing | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Icons/business-payments/shopping-cart | fill | `#FFFFFF` | `button.fab.primary.icon` | `var(--ach-button-fab-primary-icon)` |
| Vector | fill | `#FFFFFF` | `button.fab.primary.icon` | `var(--ach-button-fab-primary-icon)` |

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
