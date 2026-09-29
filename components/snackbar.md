---
id: snackbar
name: Snackbar
category: feedback
figma_component_name: "Snackbar"
figma_url: "https://www.figma.com/design//?node-id=1595-28714"
status: draft
tokens_used:
  - snackbar.neutral.background
  - padding.3
  - padding.4
  - snackbar.neutral.icon-bg
  - snackbar.icon
  - snackbar.title-text
  - snackbar.description-text
  - borderRadius.infinite
  - padding.1
  - hacks to fit scale.6
  - button.link.primary.text
  - snackbar.close-icon
---

# Snackbar

> A brief, non-intrusive message that appears temporarily at the bottom of the screen.
AKA: Toast, Toast Notification, Flash Message, Snack Bar, Inline Notification, Pop-up Message

## Code contract

```typescript
interface SnackbarProps {
  /** Toggle: Has Action */
  Has Action?: boolean;
  /** Toggle: Dismissible */
  Dismissible?: boolean;
  /** Toggle: Has Title */
  Has Title?: boolean;
  /** Text content: Title Text */
  Title Text?: React.ReactNode;
  /** Text content: Description Text */
  Description Text?: React.ReactNode;
  /** Toggle: Has Description */
  Has Description?: boolean;
  /** Toggle: Show Icon */
  Show Icon?: boolean;
  /** Visual variant: Status */
  Status?: 'Neutral' | 'Warning' | 'Info' | 'Error' | 'Success';
  children?: React.ReactNode;
  className?: string;
}
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Status | `Neutral`, `Warning`, `Info`, `Error`, `Success` | `Neutral` | Visual variant: Status |

## Anatomy

```
1. [Root] Status=Neutral (COMPONENT)
  2. [Icon] Snackbar Icon (INSTANCE)
    3. [Icon] Icons/common-actions/hourglass-empty (INSTANCE)
      4. [Element] Vector (VECTOR)
  5. [Container] Content (FRAME)
    6. [Label] Title (TEXT)
    7. [Label] Description (TEXT)
  8. [Container] Button Group (SLOT)
    9. [Container] 03 Button Link v1.1 (INSTANCE)
      10. [Icon] Left icon (INSTANCE)
        11. [Element] Vector (VECTOR)
      12. [Label] Button (TEXT)
      13. [Icon] Right icon (INSTANCE)
        14. [Element] Vector (VECTOR)
  15. [Icon] Icons/ui-actions/close (INSTANCE)
    16. [Element] Vector (VECTOR)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Status=Neutral | fill | `#E5E5E5` | `snackbar.neutral.background` | `var(--ach-snackbar-neutral-background)` |
| Status=Neutral | cornerRadius | `100px` | `—` | `—` |
| Status=Neutral | paddingTop | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Status=Neutral | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Status=Neutral | paddingBottom | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Status=Neutral | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Status=Neutral | itemSpacing | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Snackbar Icon | fill | `#737373` | `snackbar.neutral.icon-bg` | `var(--ach-snackbar-neutral-icon-bg)` |
| Snackbar Icon | cornerRadius | `100px` | `—` | `—` |
| Icons/common-actions/hourglass-empty | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#FFFFFF` | `snackbar.icon` | `var(--ach-snackbar-icon)` |
| Content | itemSpacing | `2px` | `—` | `—` |
| Title | fill | `#262626` | `snackbar.title-text` | `var(--ach-snackbar-title-text)` |
| Title | fontSize | `14px` | `—` | `—` |
| Description | fill | `#525252` | `snackbar.description-text` | `var(--ach-snackbar-description-text)` |
| Description | fontSize | `12px` | `—` | `—` |
| 03 Button Link v1.1 | cornerRadius | `9999px` | `borderRadius.infinite` | `var(--ach-borderRadius-infinite)` |
| 03 Button Link v1.1 | paddingTop | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 03 Button Link v1.1 | paddingRight | `10px` | `—` | `—` |
| 03 Button Link v1.1 | paddingBottom | `4px` | `padding.1` | `var(--ach-padding-1)` |
| 03 Button Link v1.1 | paddingLeft | `10px` | `—` | `—` |
| 03 Button Link v1.1 | itemSpacing | `6px` | `hacks to fit scale.6` | `var(--ach-hacks to fit scale-6)` |
| Left icon | fill | `#262626` | `button.link.primary.text` | `var(--ach-button-link-primary-text)` |
| Vector | fill | `#262626` | `button.link.primary.text` | `var(--ach-button-link-primary-text)` |
| Button | fill | `#262626` | `button.link.primary.text` | `var(--ach-button-link-primary-text)` |
| Button | fontSize | `10px` | `—` | `—` |
| Right icon | fill | `#262626` | `button.link.primary.text` | `var(--ach-button-link-primary-text)` |
| Vector | fill | `#262626` | `button.link.primary.text` | `var(--ach-button-link-primary-text)` |
| Icons/ui-actions/close | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `snackbar.close-icon` | `var(--ach-snackbar-close-icon)` |

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
