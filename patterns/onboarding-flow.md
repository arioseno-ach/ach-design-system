---
kind: template
---

# Onboarding flow

First-run path that collects the minimum needed to use the product, then lands the user in the main app.

## Uses

- [Wizard](./wizard.md) for sequenced setup
- [Top bar](./top-bar.md)
- [Bottom action bar](./bottom-action-bar.md)
- [Dialog](./dialog.md) for skip / leave
- [Button](../components/button.md), [Input field](../components/input-field.md), Stepper

## Structure

Typical sequence (adjust in `context/product-overview.md`):

1. Welcome / value (optional, skippable)
2. Required account or profile fields
3. Required permissions or preferences
4. Confirmation → home

## Rules

- Ask only for what the product cannot proceed without. Defer the rest.
- Skip is allowed on optional steps; not on legally required steps (`context/legal-rules.md`).
- Copy follows `context/brand-voice.md`.
- Do not re-onboard without a user-initiated reset.

## Do not

- Duplicate wizard layout rules; inherit them.
- Introduce a different primary-button placement than the bottom action bar.
