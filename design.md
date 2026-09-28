# Design rules

Global rules for every screen, component, and piece of copy. Product-specific constraints live in `business-context/`.

## Principles

1. **Clarity over decoration.** Every control should have one job.
2. **Reuse before inventing.** Use tokens, then components, then patterns, then templates.
3. **Progressive disclosure.** Show the next required step; hide optional complexity until needed.
4. **Trust through consistency.** Same action, same label, same placement.
5. **Accessible by default.** Meet the baseline in `foundations/accessibility.md`.

## Brand voice

Default tone is calm, direct, and professional. Prefer short sentences and concrete verbs.

- Do: “Continue”, “Save changes”, “Review your details”.
- Don’t: “Let’s go!”, “Oops”, slang, or internal jargon unless defined in `business-context/brand-voice.md`.

Full terminology and do/don’t lists: `business-context/brand-voice.md`.

## Visual rules

- Use only values from `tokens/tokens.json` (and the generated `tokens.css`).
- Do not introduce new colors, type sizes, or spacing steps without updating tokens first.
- Follow foundations for how tokens combine: `foundations/color.md`, `typography.md`, `spacing.md`.

## Interaction rules

- Primary action: one per view, rightmost / most prominent.
- Destructive actions require confirmation via the dialog pattern.
- Loading, empty, error, and disabled states are required for interactive components.
- Do not block the user without an explanation and a recovery path.

## Agent rules

- Do not redefine a component inside a pattern or template. Link to it.
- If product copy conflicts with brand-voice rules, follow `business-context/` and log the conflict.
- After a correction from review or production, write it in `changelog/corrections-log.md` and update the matching rule file.
