---
id: dialog
name: Dialog
category: feedback
figma_component_name: "Dialog"
figma_url: "https://www.figma.com/design//?node-id=1103-1933"
status: draft
tokens_used:
  - dialog.background
  - borderRadius.lg
  - dialog.border
  - padding.4
  - dialog.title-text
  - dialog.icon
  - padding.2
  - padding.1
  - button.outlined.primary.border
  - borderRadius.infinite
  - button.outlined.primary.text
  - button.primary.background
  - button.primary.text
child_components:
  - .dialog-header
  - .dialog-footer
---

# Dialog

> A modal overlay that requires user interaction before returning to the main content.
AKA: Modal, Popup, Alert Dialog, Confirmation Dialog, Modal Window, Overlay

## Relationships

**Child components (used inside this component):**
- [`.Dialog Header`](./.dialog-header.component.md)
- [`.Dialog Footer`](./.dialog-footer.component.md)

## Code contract

```typescript
interface DialogProps {
  /** Visual variant: Overlay */
  Overlay?: 'true' | 'false';
  children?: React.ReactNode; // Accepts: .Dialog Header, .Dialog Footer
  className?: string;
}
```

## Usage

```tsx
<Dialog>
  <.DialogHeader />
  <.DialogHeader />
  <.DialogFooter />
  <.DialogFooter />
</Dialog>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Overlay | `true`, `false` | `true` | Visual variant: Overlay |

## Anatomy

```
1. [Root] Overlay=true (COMPONENT)
  2. [Container] Overlay (FRAME)
    3. [Element] bg (RECTANGLE)
  4. [Container] Dialog (FRAME)
    5. [Container] .Dialog Header (INSTANCE)
      6. [Container] Content (SLOT)
        7. [Container] Drawer Title (FRAME)
          8. [Label] Dialog Title (TEXT)
        9. [Icon] Icons/ui-actions/close (INSTANCE)
          10. [Element] Vector (VECTOR)
    11. [Container] Drawer Content (FRAME)
      12. [Container] Main Content (SLOT)
    13. [Container] .Dialog Footer (INSTANCE)
      14. [Container] Content (SLOT)
        15. [Container] Button Group (FRAME)
          16. [Container] 02 Button Outlined v1.1 (INSTANCE)
            17. [Icon] Left icon (INSTANCE)
              18. [Element] Vector (VECTOR)
            19. [Label] Button (TEXT)
            20. [Icon] Right icon (INSTANCE)
              21. [Element] Vector (VECTOR)
          22. [Container] 01 Button Solid  v1.1 (INSTANCE)
            23. [Icon] Left icon (INSTANCE)
              24. [Element] Vector (VECTOR)
            25. [Label] Button (TEXT)
            26. [Icon] Right icon (INSTANCE)
              27. [Element] Vector (VECTOR)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Overlay=true | itemSpacing | `10px` | `—` | `—` |
| Overlay | fill | `#000000` | `—` | `—` |
| Overlay | itemSpacing | `10px` | `—` | `—` |
| bg | fill | `#000000` | `—` | `—` |
| Dialog | fill | `#FFFFFF` | `dialog.background` | `var(--ach-dialog-background)` |
| Dialog | cornerRadius | `16px` | `borderRadius.lg` | `var(--ach-borderRadius-lg)` |
| .Dialog Header | stroke | `#DCDCDC` | `dialog.border` | `var(--ach-dialog-border)` |
| .Dialog Header | paddingTop | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .Dialog Header | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .Dialog Header | paddingBottom | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .Dialog Header | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .Dialog Header | itemSpacing | `10px` | `—` | `—` |
| Content | itemSpacing | `175px` | `—` | `—` |
| Drawer Title | itemSpacing | `10px` | `—` | `—` |
| Dialog Title | fill | `#262626` | `dialog.title-text` | `var(--ach-dialog-title-text)` |
| Dialog Title | fontSize | `20px` | `—` | `—` |
| Icons/ui-actions/close | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `dialog.icon` | `var(--ach-dialog-icon)` |
| Drawer Content | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Drawer Content | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Drawer Content | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Drawer Content | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Main Content | itemSpacing | `10px` | `—` | `—` |
| .Dialog Footer | stroke | `#DCDCDC` | `dialog.border` | `var(--ach-dialog-border)` |
| .Dialog Footer | paddingTop | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .Dialog Footer | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .Dialog Footer | paddingBottom | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .Dialog Footer | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| .Dialog Footer | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Content | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Button Group | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 Button Outlined v1.1 | stroke | `#DCDCDC` | `button.outlined.primary.border` | `var(--ach-button-outlined-primary-border)` |
| 02 Button Outlined v1.1 | cornerRadius | `9999px` | `borderRadius.infinite` | `var(--ach-borderRadius-infinite)` |
| 02 Button Outlined v1.1 | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 Button Outlined v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Button Outlined v1.1 | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 Button Outlined v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Button Outlined v1.1 | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Left icon | fill | `#262626` | `button.outlined.primary.text` | `var(--ach-button-outlined-primary-text)` |
| Vector | fill | `#262626` | `button.outlined.primary.text` | `var(--ach-button-outlined-primary-text)` |
| Button | fill | `#262626` | `button.outlined.primary.text` | `var(--ach-button-outlined-primary-text)` |
| Button | fontSize | `14px` | `—` | `—` |
| Right icon | fill | `#262626` | `button.outlined.primary.text` | `var(--ach-button-outlined-primary-text)` |
| Vector | fill | `#262626` | `button.outlined.primary.text` | `var(--ach-button-outlined-primary-text)` |
| 01 Button Solid  v1.1 | fill | `#171717` | `button.primary.background` | `var(--ach-button-primary-background)` |
| 01 Button Solid  v1.1 | cornerRadius | `9999px` | `borderRadius.infinite` | `var(--ach-borderRadius-infinite)` |
| 01 Button Solid  v1.1 | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 01 Button Solid  v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 01 Button Solid  v1.1 | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 01 Button Solid  v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 01 Button Solid  v1.1 | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Left icon | fill | `#FFFFFF` | `button.primary.text` | `var(--ach-button-primary-text)` |
| Vector | fill | `#FFFFFF` | `button.primary.text` | `var(--ach-button-primary-text)` |
| Button | fill | `#FFFFFF` | `button.primary.text` | `var(--ach-button-primary-text)` |
| Button | fontSize | `14px` | `—` | `—` |
| Right icon | fill | `#FFFFFF` | `button.primary.text` | `var(--ach-button-primary-text)` |
| Vector | fill | `#FFFFFF` | `button.primary.text` | `var(--ach-button-primary-text)` |

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
id: .dialog-header
name: .DialogHeader
category: layout
figma_component_name: ".Dialog Header"
figma_url: "https://www.figma.com/design//?node-id=1103-1960"
status: draft
tokens_used:
  - dialog.border
  - padding.4
  - dialog.title-text
  - dialog.icon
parent_components:
  - dialog
---

# .DialogHeader

## Relationships

**Parent components (this component is used inside):**
- [`Dialog`](./dialog.component.md)

## Code contract

```typescript
interface .DialogHeaderProps {
  /** Visual variant: Size */
  Size?: 'M';
  /** Visual variant: Title */
  Title?: 'False' | 'True';
  children?: React.ReactNode;
  className?: string;
}
```

## Usage

> This component is designed to be used inside [`Dialog`](./dialog.component.md).

```tsx
<Dialog>
  <.DialogHeader />
  <.DialogHeader />
</Dialog>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Size | `M` | `M` | Visual variant: Size |
| Title | `False`, `True` | `True` | Visual variant: Title |

## Anatomy

```
1. [Root] Size=M, Title=True (COMPONENT)
  2. [Container] Content (SLOT)
    3. [Container] Drawer Title (FRAME)
      4. [Label] Dialog Title (TEXT)
    5. [Icon] Icons/ui-actions/close (INSTANCE)
      6. [Element] Vector (VECTOR)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Size=M, Title=True | stroke | `#DCDCDC` | `dialog.border` | `var(--ach-dialog-border)` |
| Size=M, Title=True | paddingTop | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Size=M, Title=True | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Size=M, Title=True | paddingBottom | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Size=M, Title=True | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Size=M, Title=True | itemSpacing | `10px` | `—` | `—` |
| Content | itemSpacing | `175px` | `—` | `—` |
| Drawer Title | itemSpacing | `10px` | `—` | `—` |
| Dialog Title | fill | `#262626` | `dialog.title-text` | `var(--ach-dialog-title-text)` |
| Dialog Title | fontSize | `20px` | `—` | `—` |
| Icons/ui-actions/close | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#262626` | `dialog.icon` | `var(--ach-dialog-icon)` |

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
id: .dialog-footer
name: .DialogFooter
category: layout
figma_component_name: ".Dialog Footer"
figma_url: "https://www.figma.com/design//?node-id=1103-2010"
status: draft
tokens_used:
  - dialog.border
  - padding.4
  - padding.1
  - padding.2
  - button.outlined.primary.border
  - borderRadius.infinite
  - button.outlined.primary.text
  - button.primary.background
  - button.primary.text
parent_components:
  - dialog
---

# .DialogFooter

## Relationships

**Parent components (this component is used inside):**
- [`Dialog`](./dialog.component.md)

## Code contract

```typescript
interface .DialogFooterProps {
  /** Visual variant: Type */
  Type?: '2 Button Right' | '2 Full-width Button' | 'Single Full-width Button';
  children?: React.ReactNode;
  className?: string;
}
```

## Usage

> This component is designed to be used inside [`Dialog`](./dialog.component.md).

```tsx
<Dialog>
  <.DialogFooter />
  <.DialogFooter />
</Dialog>
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Type | `2 Button Right`, `2 Full-width Button`, `Single Full-width Button` | `2 Button Right` | Visual variant: Type |

## Anatomy

```
1. [Root] Type=2 Button Right (COMPONENT)
  2. [Container] Content (SLOT)
    3. [Container] Button Group (FRAME)
      4. [Container] 02 Button Outlined v1.1 (INSTANCE)
        5. [Icon] Left icon (INSTANCE)
          6. [Element] Vector (VECTOR)
        7. [Label] Button (TEXT)
        8. [Icon] Right icon (INSTANCE)
          9. [Element] Vector (VECTOR)
      10. [Container] 01 Button Solid  v1.1 (INSTANCE)
        11. [Icon] Left icon (INSTANCE)
          12. [Element] Vector (VECTOR)
        13. [Label] Button (TEXT)
        14. [Icon] Right icon (INSTANCE)
          15. [Element] Vector (VECTOR)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Type=2 Button Right | stroke | `#DCDCDC` | `dialog.border` | `var(--ach-dialog-border)` |
| Type=2 Button Right | paddingTop | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Type=2 Button Right | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Type=2 Button Right | paddingBottom | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Type=2 Button Right | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Type=2 Button Right | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Content | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Button Group | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 Button Outlined v1.1 | stroke | `#DCDCDC` | `button.outlined.primary.border` | `var(--ach-button-outlined-primary-border)` |
| 02 Button Outlined v1.1 | cornerRadius | `9999px` | `borderRadius.infinite` | `var(--ach-borderRadius-infinite)` |
| 02 Button Outlined v1.1 | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 Button Outlined v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Button Outlined v1.1 | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 02 Button Outlined v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 02 Button Outlined v1.1 | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Left icon | fill | `#262626` | `button.outlined.primary.text` | `var(--ach-button-outlined-primary-text)` |
| Vector | fill | `#262626` | `button.outlined.primary.text` | `var(--ach-button-outlined-primary-text)` |
| Button | fill | `#262626` | `button.outlined.primary.text` | `var(--ach-button-outlined-primary-text)` |
| Button | fontSize | `14px` | `—` | `—` |
| Right icon | fill | `#262626` | `button.outlined.primary.text` | `var(--ach-button-outlined-primary-text)` |
| Vector | fill | `#262626` | `button.outlined.primary.text` | `var(--ach-button-outlined-primary-text)` |
| 01 Button Solid  v1.1 | fill | `#171717` | `button.primary.background` | `var(--ach-button-primary-background)` |
| 01 Button Solid  v1.1 | cornerRadius | `9999px` | `borderRadius.infinite` | `var(--ach-borderRadius-infinite)` |
| 01 Button Solid  v1.1 | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 01 Button Solid  v1.1 | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 01 Button Solid  v1.1 | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| 01 Button Solid  v1.1 | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| 01 Button Solid  v1.1 | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Left icon | fill | `#FFFFFF` | `button.primary.text` | `var(--ach-button-primary-text)` |
| Vector | fill | `#FFFFFF` | `button.primary.text` | `var(--ach-button-primary-text)` |
| Button | fill | `#FFFFFF` | `button.primary.text` | `var(--ach-button-primary-text)` |
| Button | fontSize | `14px` | `—` | `—` |
| Right icon | fill | `#FFFFFF` | `button.primary.text` | `var(--ach-button-primary-text)` |
| Vector | fill | `#FFFFFF` | `button.primary.text` | `var(--ach-button-primary-text)` |

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
