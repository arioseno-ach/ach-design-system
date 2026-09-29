# Dialog

## Purpose

Interrupts the current task for a decision or short piece of information. Not a full page.

## Composed of

- Title + body text
- [Button](../components/button.md) actions (1–2, rarely 3)
- Optional [Input](../components/input.md) only for short confirmation (e.g. type to confirm)

## Behavior

- Modal. Focus trapped. Esc and overlay click dismiss only if the action is non-destructive and discardable.
- Return focus to the opener on close.
- Role: `dialog` with labelled-by title.

## Rules

- Destructive confirmations: title names the action; primary button is destructive; secondary is cancel.
- Do not nest dialogs.
- If the content needs a stepper, top bar, or long form, use a template/screen instead of a dialog.
