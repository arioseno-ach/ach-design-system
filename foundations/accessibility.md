# Accessibility

Baseline rules for every component, pattern, and template.

## Contrast and type

- Text vs background: at least 4.5:1 for body, 3:1 for large title text.
- UI components and graphics: at least 3:1 against adjacent colors.
- Do not convey meaning with color alone.

## Interaction

- Minimum hit target: 44×44 CSS pixels.
- Keyboard: all interactive elements focusable in a logical order.
- Visible focus ring required; do not remove outline without a replacement.
- Dialogs trap focus while open and return focus on close. See `patterns/dialog.pattern.md`.

## Semantics and names

- Use native elements (`button`, `input`, `label`) unless a component spec requires otherwise.
- Every input has a visible label (placeholder is not a label).
- Images that convey meaning have alternative text; decorative images are hidden from AT.
- Status messages (error, success, loading) are announced.

## Motion

- Honor `prefers-reduced-motion`. Essential information must not depend on animation.
