---
id: alert
name: Alert
category: feedback
figma_component_name: "Alert"
figma_url: "https://www.figma.com/design//?node-id=1245-21216"
status: draft
tokens_used:
  - alert.neutral.background
  - alert.neutral.border
  - borderRadius.sm
  - padding.3
  - padding.4
  - alert.neutral.icon
  - padding.1
  - alert.neutral.title
  - alert.neutral.text
  - padding.2
  - borderRadius.infinite
  - button.link.primary.text
---

# Alert

> Alert — Inform users of important changes prominently.
AKA: Notification, Feedback, Message, Banner, Callout.

Variant: Status (Neutral, Success, Info, Warning, Error)
Toggles: Has Title, Has Action, Dismissible
Text: Title Text, Description Text
Instance Swap: Status Icon (swap to any icon from your library)

Uses library icons and button components.

## Code contract

```typescript
interface AlertProps {
  /** Toggle: Has Title */
  Has Title?: boolean;
  /** Toggle: Has Action */
  Has Action?: boolean;
  /** Toggle: Dismissible */
  Dismissible?: boolean;
  /** Text content: Title Text */
  Title Text?: React.ReactNode;
  /** Text content: Description Text */
  Description Text?: React.ReactNode;
  /** Slot: Status Icon */
  Status Icon?: React.ReactNode;
  /** Visual variant: Status */
  Status?: 'Neutral' | 'Success' | 'Info' | 'Warning' | 'Error';
  /** Visual variant: Style */
  Style?: 'Soft';
  children?: React.ReactNode;
  className?: string;
}
```

## Variants

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| Status | `Neutral`, `Success`, `Info`, `Warning`, `Error` | `Neutral` | Visual variant: Status |
| Style | `Soft` | `Soft` | Visual variant: Style |

## Anatomy

```
1. [Root] Status=Neutral, Style=Soft (COMPONENT)
  2. [Icon] Icons/others/error-circle-rounded (INSTANCE)
    3. [Element] Vector (VECTOR)
  4. [Container] Content (FRAME)
    5. [Label] Title (TEXT)
    6. [Label] Description (TEXT)
  7. [Container] Button Group (SLOT)
    8. [Container] ActionButton (INSTANCE)
      9. [Icon] Left icon (INSTANCE)
        10. [Element] Vector (VECTOR)
      11. [Label] Button (TEXT)
      12. [Icon] Right icon (INSTANCE)
        13. [Element] Vector (VECTOR)
  14. [Icon] Icons/ui-actions/close (INSTANCE)
    15. [Element] Vector (VECTOR)
```

## Design tokens mapping

| Layer | Property | Raw value | Token | CSS variable |
| :--- | :--- | :--- | :--- | :--- |
| Status=Neutral, Style=Soft | fill | `#F5F5F5` | `alert.neutral.background` | `var(--ach-alert-neutral-background)` |
| Status=Neutral, Style=Soft | stroke | `#E5E5E5` | `alert.neutral.border` | `var(--ach-alert-neutral-border)` |
| Status=Neutral, Style=Soft | cornerRadius | `8px` | `borderRadius.sm` | `var(--ach-borderRadius-sm)` |
| Status=Neutral, Style=Soft | paddingTop | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Status=Neutral, Style=Soft | paddingRight | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Status=Neutral, Style=Soft | paddingBottom | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Status=Neutral, Style=Soft | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| Status=Neutral, Style=Soft | itemSpacing | `12px` | `padding.3` | `var(--ach-padding-3)` |
| Icons/others/error-circle-rounded | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `alert.neutral.icon` | `var(--ach-alert-neutral-icon)` |
| Content | itemSpacing | `4px` | `padding.1` | `var(--ach-padding-1)` |
| Title | fill | `#262626` | `alert.neutral.title` | `var(--ach-alert-neutral-title)` |
| Title | fontSize | `14px` | `—` | `—` |
| Description | fill | `#525252` | `alert.neutral.text` | `var(--ach-alert-neutral-text)` |
| Description | fontSize | `12px` | `—` | `—` |
| Button Group | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| ActionButton | cornerRadius | `9999px` | `borderRadius.infinite` | `var(--ach-borderRadius-infinite)` |
| ActionButton | paddingTop | `8px` | `padding.2` | `var(--ach-padding-2)` |
| ActionButton | paddingRight | `16px` | `padding.4` | `var(--ach-padding-4)` |
| ActionButton | paddingBottom | `8px` | `padding.2` | `var(--ach-padding-2)` |
| ActionButton | paddingLeft | `16px` | `padding.4` | `var(--ach-padding-4)` |
| ActionButton | itemSpacing | `8px` | `padding.2` | `var(--ach-padding-2)` |
| Left icon | fill | `#262626` | `button.link.primary.text` | `var(--ach-button-link-primary-text)` |
| Vector | fill | `#262626` | `button.link.primary.text` | `var(--ach-button-link-primary-text)` |
| Button | fill | `#262626` | `button.link.primary.text` | `var(--ach-button-link-primary-text)` |
| Button | fontSize | `14px` | `—` | `—` |
| Right icon | fill | `#262626` | `button.link.primary.text` | `var(--ach-button-link-primary-text)` |
| Vector | fill | `#262626` | `button.link.primary.text` | `var(--ach-button-link-primary-text)` |
| Icons/ui-actions/close | fill | `#FFFFFF` | `—` | `—` |
| Vector | fill | `#737373` | `alert.neutral.icon` | `var(--ach-alert-neutral-icon)` |

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
