---
id: button
name: Button
category: primitive
figma_component_name: "Button"
status: draft
tokens_used:
  - color.brand.500
  - color.brand.600
  - color.neutral.0
  - color.neutral.200
  - color.feedback.danger
  - space.12
  - space.16
  - radius.md
---

# Button

## Purpose
Triggers a single user action. Exactly one primary button is permitted per view.

---

## Code Contract (API Specification)

```typescript
export interface ButtonProps extends React.ButtonHTMLAttributes<HTMLButtonElement> {
  /** Visual emphasis level */
  variant?: 'primary' | 'secondary' | 'tertiary' | 'destructive';
  /** Size scale */
  size?: 'sm' | 'md' | 'lg';
  /** Displays loading spinner while preserving stable dimensions */
  loading?: boolean;
  /** Disables click interaction and applies muted visuals */
  disabled?: boolean;
  /** Optional icon rendered before the text label */
  leadingIcon?: React.ReactNode;
  /** Optional icon rendered after the text label */
  trailingIcon?: React.ReactNode;
  /** Button label content */
  children: React.ReactNode;
}
```

---

## Variants

| Variant | Purpose | Visual Signature |
| :--- | :--- | :--- |
| **Primary** | Main forward action for the screen | Filled `color.brand.500`, text `color.neutral.0` |
| **Secondary** | Supporting or alternative action | Border `color.neutral.200`, background `color.neutral.0` |
| **Tertiary** | Low-emphasis, link-like actions | Transparent background, text `color.brand.500` |
| **Destructive** | Harmful or irreversible action (must pair with confirmation dialog) | Fill or text `color.feedback.danger` |

---

## Anatomy

```
┌───────────────────────────────────────────────┐
│  [leadingIcon]       Label     [trailingIcon] │
└───────────────────────────────────────────────┘
```
- **Label**: Required. Must use actionable, clear verbs (e.g. "Continue", "Save changes").
- **Icons**: Optional 16x16px or 20x20px icon. Never place competing multiple labels inside.

---

## Tokens Mapping

| Property | Token | CSS Custom Property | Value |
| :--- | :--- | :--- | :--- |
| Radius | `radius.md` | `var(--ach-radius-md)` | `8px` |
| Padding (Y / X) | `space.12`, `space.16` | `var(--ach-space-12)` `var(--ach-space-16)` | `12px 16px` |
| Primary Background | `color.brand.500` | `var(--ach-color-brand-500)` | `#1F4EA3` |
| Primary Hover | `color.brand.600` | `var(--ach-color-brand-600)` | `#173B7C` |
| Primary Label | `color.neutral.0` | `var(--ach-color-neutral-0)` | `#FFFFFF` |
| Secondary Border | `color.neutral.200` | `var(--ach-color-neutral-200)` | `#D9D9DE` |
| Secondary Background | `color.neutral.0` | `var(--ach-color-neutral-0)` | `#FFFFFF` |
| Destructive Fill/Text| `color.feedback.danger`| `var(--ach-color-feedback-danger)` | `#B42318` |

---

## States

| State | Visual Treatment | Implementation Notes |
| :--- | :--- | :--- |
| **Default** | Standard resting token styles | Baseline |
| **Hover** | Darken background by 1 shade (`brand.600`) | `:hover:not(:disabled)` |
| **Pressed / Active** | Scale `0.98` or deepest shade | `:active:not(:disabled)` |
| **Focus** | 2px solid ring with 2px offset | `:focus-visible` |
| **Disabled** | Muted opacity (40%), `cursor: not-allowed` | Must have nearby explanatory helper text |
| **Loading** | Spinner replaces label; width is preserved | `aria-busy="true"`, prevent multiple clicks |

---

## Rules & Constraints (Agent Adherence)

| Do ✅ | Don't ❌ |
| :--- | :--- |
| `<Button variant="primary">Continue</Button>` | `<button style={{ background: '#1F4EA3' }}>` (Hardcoded hex) |
| Exactly **one** primary button per screen or dialog | Two primary buttons competing on the same view |
| Show helper text explaining why button is disabled | Disabling a button without telling the user how to unblock |
| Preserve exact button dimensions during `loading` state | Shrinking or resizing button width when spinner appears |
| Keep button interactive elements flat (pure `<button>`) | Nesting `<a>`, `<input>`, or other buttons inside |
