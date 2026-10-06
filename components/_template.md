---
id: component-name
name: ComponentName
category: primitive # primitive | layout | feedback | navigation
figma_component_name: "ComponentName"
figma_url: "https://www.figma.com/design/..."
status: draft # draft | in-review | stable | deprecated
tokens_used:
  - color.brand.500
  - color.neutral.900
  - space.12
  - space.16
  - radius.md
---

# ComponentName

## Purpose
A concise 1-2 sentence description explaining what this component does and when to use it.

---

## Code Contract (API Specification)

```typescript
export interface ComponentNameProps {
  /** Visual variant of the component */
  variant?: 'primary' | 'secondary' | 'tertiary';
  /** Size scale */
  size?: 'sm' | 'md' | 'lg';
  /** Whether the component is in a loading/busy state */
  loading?: boolean;
  /** Whether the component is disabled */
  disabled?: boolean;
  /** Accessible label if text content is not provided */
  'aria-label'?: string;
  /** Children or text label */
  children?: React.ReactNode;
}
```

---

## Variants & Properties

| Variant / Prop | Values | Default | Purpose |
| :--- | :--- | :--- | :--- |
| `variant` | `primary`, `secondary`, `tertiary` | `primary` | Visual priority and emphasis |
| `size` | `sm` (32px), `md` (40px), `lg` (48px) | `md` | Scale and touch-target sizing |
| `loading` | `boolean` | `false` | Shows spinner and locks interaction |
| `disabled` | `boolean` | `false` | Muted appearance, prevents click |

---

## Anatomy

```
┌───────────────────────────────────────────────┐
│  [Leading Icon]      Label     [Trailing Icon]│
└───────────────────────────────────────────────┘
```

1. **Container**: Bounded interactive area with border and background tokens.
2. **Leading / Trailing Icon (Optional)**: 16x16px or 20x20px icon.
3. **Label**: Concise, action-oriented text.

---

## Design Tokens Mapping

| Property | Design Token | CSS Custom Property | Value |
| :--- | :--- | :--- | :--- |
| Background (Default) | `color.brand.500` | `var(--ach-color-brand-500)` | `#1F4EA3` |
| Background (Hover) | `color.brand.600` | `var(--ach-color-brand-600)` | `#173B7C` |
| Text Color | `color.neutral.0` | `var(--ach-color-neutral-0)` | `#FFFFFF` |
| Border Radius | `radius.md` | `var(--ach-radius-md)` | `8px` |
| Padding (Y / X) | `space.12`, `space.16` | `var(--ach-space-12)` `var(--ach-space-16)` | `12px 16px` |

---

## States

| State | Visual Treatment | CSS Selector / Attribute |
| :--- | :--- | :--- |
| **Default** | Standard resting token values | `:not(:disabled)` |
| **Hover** | Surface darkens by one step | `:hover:not(:disabled)` |
| **Active / Pressed** | Slight scale or deeper tone | `:active:not(:disabled)` |
| **Focus** | 2px solid ring with 2px offset | `:focus-visible` |
| **Disabled** | 40% opacity, `cursor: not-allowed` | `:disabled`, `[aria-disabled="true"]` |
| **Loading** | Content replaced by spinner, stable width | `[data-loading="true"]`, `aria-busy="true"` |

---

## Accessibility (a11y)

- **Keyboard Support**: Must be activatable via `Enter` and `Space`.
- **Focus Indicator**: Visible outline with at least 3:1 contrast against background.
- **Screen Readers**: If icon-only, `aria-label` is mandatory. When loading, announce `aria-busy="true"`.

---

## Do's and Don'ts (Agent Strict Constraints)

| Do ✅ | Don't ❌ |
| :--- | :--- |
| Use predefined tokens: `var(--ach-color-brand-500)` | Hardcode colors: `style={{ backgroundColor: '#1F4EA3' }}` |
| Provide helper text when a button is disabled | Disable an element with no explanation to the user |
| Use action-oriented verbs from `brand-voice.md` | Use generic, informal labels like "Click here" or "Go" |
| Maintain stable dimensions when transitioning to loading | Collapse or resize component width during loading state |
