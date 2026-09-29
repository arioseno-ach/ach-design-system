# Onboarding flow

First-run path that collects the minimum needed to use the product, then lands the user in the main app.

## Uses

- [Wizard](./wizard.template.md) for sequenced setup
- [Top bar](../patterns/top-bar.pattern.md)
- [Bottom action bar](../patterns/bottom-action-bar.pattern.md)
- [Dialog](../patterns/dialog.pattern.md) for skip / leave
- [Button](../components/button.md), [Input](../components/input.md), [Stepper](../components/stepper.md)

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
