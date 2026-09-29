---
id: file-input
name: FileInput
category: primitive
figma_component_name: "File Input"
figma_url: "https://www.figma.com/design//?node-id=1327-263"
status: draft
tokens_used:
  - padding.2
  - padding.1
  - file-input.label.text
  - file-input.label.required
  - badge.neutral.background
  - borderRadius.sm
  - 3xs
  - xs
  - 2xs
  - badge.solid.secondary.icon
  - badge.neutral.icon
  - text.ach-color-text-secondary
  - file-input.field.background
  - file-input.field.border
  - padding.3
  - button.outlined.neutral.border
  - borderRadius.infinite
  - hacks to fit scale.6
  - button.outlined.neutral.text
  - general.foreground
  - file-input.placeholder.text
  - file-input.helper.text
---

# FileInput

> A file upload input allowing users to browse and select files from their device.
AKA: File Upload, Upload Input, File Picker, File Selector, Upload Button, Dropzone

## Code contract

```typescript
interface FileInputProps {
  /** Text content: File Name */
  File Name?: React.ReactNode;
  /** Text content: Placeholder */
  Placeholder?: React.ReactNode;
  /** Text content: Supporting Text */
  Supporting Text?: React.ReactNode;
  /** Text content: Label */
  Label?: React.ReactNode;
  /** Toggle: Show Label */
  Show Label?: boolean;
  /** Toggle: Required */
  Required?: boolean;
  /** Text content: Helper Text */
  Helper Text?: React.ReactNode;
  /** Toggle: Show Helper Text */
  Show Helper Text?: boolean;
  /** Toggle: Show Supporting Text */
  Show Supporting Text?: boolean;
  /** Toggle: Show Status */
  Show Status?: boolean;
  /** Visual variant: State */
  State?: 'Placeholder' | 'Filled' | 'Error' | 'Disabled' | 'Focus';
  children?: React.ReactNode;
  className?: string;
}
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| State | `Placeholder`, `Filled`, `Error`, `Disabled`, `Focus` | `Placeholder` | Visual variant: State |

## Anatomy

```
1. [Root] State=Placeholder (COMPONENT)
  2. [Container] Label Row (FRAME)
    3. [Container] Title (FRAME)
      4. [Label] Label (TEXT)
      5. [Label] Required (TEXT)
    6. [Badge] Status Badge (INSTANCE)
      7. [Icon] Left icon (INSTANCE)
        8. [Element] Vector (VECTOR)
      9. [Label] Label (TEXT)
      10. [Icon] Right icon (INSTANCE)
        11. [Element] Vector (VECTOR)
  12. [Container] Row (FRAME)
    13. [Container] Button (INSTANCE)
      14. [Icon] Left icon (INSTANCE)
        15. [Element] Vector (VECTOR)
      16. [Label] Button (TEXT)
      17. [Icon] Right icon (INSTANCE)
        18. [Element] Vector (VECTOR)
    19. [Label] Placeholder (TEXT)
  20. [Label] Helper Text (TEXT)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| State=Placeholder | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Label Row | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Title | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Label | fill | `#262626` | `file-input.label.text` | `var(--ach-file-input-label-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Required | fill | `#A00000` | `file-input.label.required` | `var(--ach-file-input-label-required)` |
| Required | fontSize | `14px` | `—` | `—` |
| Status Badge | fill | `#F5F5F5` | `badge.neutral.background` | `var(--ach-badge-neutral-background)` |
| Status Badge | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Status Badge | paddingTop | `2px` | `3xs` | `var(--ach-3xs)` |
| Status Badge | paddingRight | `8px` | `xs` | `var(--ach-xs)` |
| Status Badge | paddingBottom | `2px` | `3xs` | `var(--ach-3xs)` |
| Status Badge | paddingLeft | `8px` | `xs` | `var(--ach-xs)` |
| Status Badge | itemSpacing | `4px` | `2xs` | `var(--ach-2xs)` |
| Left icon | fill | `#FFFFFF` | `badge.solid.secondary.icon` | `var(--ach-badge-solid-secondary-icon)` |
| Vector | fill | `#737373` | `badge.neutral.icon` | `var(--ach-badge-neutral-icon)` |
| Label | fill | `#525252` | `text.ach-color-text-secondary` | `var(--ach-text-ach-color-text-secondary)` |
| Label | fontSize | `14px` | `—` | `—` |
| Right icon | fill | `#FFFFFF` | `badge.solid.secondary.icon` | `var(--ach-badge-solid-secondary-icon)` |
| Vector | fill | `#737373` | `badge.neutral.icon` | `var(--ach-badge-neutral-icon)` |
| Row | fill | `#FFFFFF` | `file-input.field.background` | `var(--ach-file-input-field-background)` |
| Row | stroke | `#DCDCDC` | `file-input.field.border` | `var(--ach-file-input-field-border)` |
| Row | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Row | paddingTop | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Row | paddingRight | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Row | paddingBottom | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Row | paddingLeft | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Row | itemSpacing | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Button | stroke | `#BDBDBD` | `button.outlined.neutral.border` | `var(--ach-button-outlined-neutral-border)` |
| Button | cornerRadius | `9999px` | `borderRadius.infinite` | `var(--ach-borderRadius-infinite)` |
| Button | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Button | paddingRight | `10px` | `—` | `—` |
| Button | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Button | paddingLeft | `10px` | `—` | `—` |
| Button | itemSpacing | `6px` | `hacks to fit scale.6` | `var(--ach-hacks to fit scale-6)` |
| Left icon | fill | `#262626` | `button.outlined.neutral.text` | `var(--ach-button-outlined-neutral-text)` |
| Vector | fill | `#0A0A0A` | `general.foreground` | `var(--ach-general-foreground)` |
| Button | fill | `#262626` | `button.outlined.neutral.text` | `var(--ach-button-outlined-neutral-text)` |
| Button | fontSize | `10px` | `—` | `—` |
| Right icon | fill | `#262626` | `button.outlined.neutral.text` | `var(--ach-button-outlined-neutral-text)` |
| Vector | fill | `#262626` | `button.outlined.neutral.text` | `var(--ach-button-outlined-neutral-text)` |
| Placeholder | fill | `#525252` | `file-input.placeholder.text` | `var(--ach-file-input-placeholder-text)` |
| Placeholder | fontSize | `14px` | `—` | `—` |
| Helper Text | fill | `#737373` | `file-input.helper.text` | `var(--ach-file-input-helper-text)` |
| Helper Text | fontSize | `14px` | `—` | `—` |

## States

| State | Present | Notes |
| :--- | :--- | :--- |
| Default | ✅ | Defined in Figma |
| Hover | ❌ | Not found — add variant or document manually |
| Pressed | ❌ | Not found — add variant or document manually |
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
