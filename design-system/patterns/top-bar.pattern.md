# Top bar

## Purpose

Persistent header for a screen: context, navigation back, and optional secondary actions.

## Composed of

- [Button](../components/button.component.md) (icon/tertiary for back and overflow)
- Title text (`foundations/typography.md` section or page title)

## Layout

- Height includes 44px hit targets.
- Horizontal padding: `space.16`.
- Left: back (if the screen is pushed). Center or left-aligned title. Right: at most two actions.

## Rules

- One title. Do not duplicate the page heading in the body unless the top bar hides on scroll (if so, keep an `h1` in the document).
- Back always returns to the previous logical step, not a random landing page.
- Destructive or rare actions go in overflow, not as a primary in the top bar.
