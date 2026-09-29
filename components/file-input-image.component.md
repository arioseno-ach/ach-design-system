---
id: file-input-image
name: FileInputImage
category: primitive
figma_component_name: "File Input Image"
figma_url: "https://www.figma.com/design//?node-id=1745-44071"
status: draft
tokens_used:
  - padding.2
  - padding.1
  - file-input-image.label.text
  - file-input-image.label.required
  - badge.neutral.background
  - borderRadius.sm
  - 3xs
  - xs
  - 2xs
  - badge.solid.secondary.icon
  - badge.neutral.icon
  - text.ach-color-text-secondary
  - file-input-image.field.background
  - file-input-image.field.border
  - padding.4
  - file-input-image.placeholder.background
  - border.ach-color-border-default
  - file-input-image.placeholder.icon
  - button.outlined.neutral.border
  - borderRadius.infinite
  - hacks to fit scale.6
  - button.outlined.neutral.text
  - general.foreground
  - file-input-image.description.text
---

# FileInputImage

> A file upload input specifically for image files, with a visual preview area.
AKA: Image Upload, Photo Upload, Image Picker, Picture Upload, Media Upload, Image Dropzone

## Code contract

```typescript
interface FileInputImageProps {
  /** Text content: Label */
  Label?: React.ReactNode;
  /** Toggle: Show Label */
  Show Label?: boolean;
  /** Toggle: Required */
  Required?: boolean;
  /** Toggle: Show Status */
  Show Status?: boolean;
  /** Text content: File Name */
  File Name?: React.ReactNode;
  /** Text content: Supporting Text */
  Supporting Text?: React.ReactNode;
  /** Toggle: Show Supporting Text */
  Show Supporting Text?: boolean;
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
  12. [Container] Content Area (FRAME)
    13. [Image] Image Placeholder (FRAME)
      14. [Icon] Image Icon (INSTANCE)
        15. [Element] Vector (VECTOR)
    16. [Container] Description (FRAME)
      17. [Container] Frame 2 (FRAME)
        18. [Container] Button (INSTANCE)
          19. [Icon] Left icon (INSTANCE)
            20. [Element] Vector (VECTOR)
          21. [Label] Button (TEXT)
          22. [Icon] Right icon (INSTANCE)
            23. [Element] Vector (VECTOR)
        24. [Label] Placeholder (TEXT)
      25. [Label] Placeholder (TEXT)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| State=Placeholder | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Label Row | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Title | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Label | fill | `#262626` | `file-input-image.label.text` | `var(--ach-file-input-image-label-text)` |
| Label | fontSize | `14px` | `—` | `—` |
| Required | fill | `#A00000` | `file-input-image.label.required` | `var(--ach-file-input-image-label-required)` |
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
| Content Area | fill | `#FFFFFF` | `file-input-image.field.background` | `var(--ach-file-input-image-field-background)` |
| Content Area | stroke | `#DCDCDC` | `file-input-image.field.border` | `var(--ach-file-input-image-field-border)` |
| Content Area | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Content Area | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Content Area | paddingRight | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Content Area | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Content Area | paddingLeft | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Content Area | itemSpacing | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Image Placeholder | fill | `#F5F5F5` | `file-input-image.placeholder.background` | `var(--ach-file-input-image-placeholder-background)` |
| Image Placeholder | stroke | `#DCDCDC` | `border.ach-color-border-default` | `var(--ach-border-ach-color-border-default)` |
| Image Placeholder | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Vector | fill | `#737373` | `file-input-image.placeholder.icon` | `var(--ach-file-input-image-placeholder-icon)` |
| Description | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Frame 2 | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
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
| Placeholder | fill | `#262626` | `file-input-image.description.text` | `var(--ach-file-input-image-description-text)` |
| Placeholder | fontSize | `14px` | `—` | `—` |
| Placeholder | fill | `#262626` | `file-input-image.description.text` | `var(--ach-file-input-image-description-text)` |
| Placeholder | fontSize | `10px` | `—` | `—` |

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
