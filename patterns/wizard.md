---
kind: template
---

# Wizard

Linear, multi-step task with a stable step list, one screen per step, and a pinned forward action.

## Uses

- [Top bar](./top-bar.md)
- [Bottom action bar](./bottom-action-bar.md)
- Stepper
- [Button](../components/button.md)
- [Input field](../components/input-field.md) as needed per step
- [Dialog](./dialog.md) for discard / destructive confirm

## Structure

1. Top bar: back + step title.
2. Stepper (optional on small screens as a compact indicator).
3. Step body (fields or review).
4. Bottom action bar: Continue / Submit on last step.

## Flow

- Continue validates the current step only.
- Back does not wipe completed step data unless the user confirms discard.
- Last step is review + submit. Success is a confirmation state, not a silent close.
- Exit mid-flow: dialog if there is unsaved work.

## Do not

- Redefine button, input, or stepper here.
- Change step count without telling the user.
