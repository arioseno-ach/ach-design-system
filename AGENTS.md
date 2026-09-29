# ACH Design System — AI Agent Instructions

> **Audience**: AI Coding Agents (Cursor, Claude Code, Antigravity, GitHub Copilot, Roo, Windsurf, etc.) and human engineers.  
> **Mission**: Act as the authoritative source of truth for all UI styling, components, interactions, and product voice across the ACH platform.

---

## 1. Absolute Constraints (Negative Rules)

Agents generating frontend code **MUST** adhere strictly to these rules:

1. **NO Hardcoded Visuals**:
   - ❌ **NEVER** write raw hex colors (e.g., `#1F4EA3`, `#FFF`), RGB, or HSL in UI code.
   - ❌ **NEVER** use arbitrary spacing or sizing numbers (e.g., `margin: 13px`, `padding: 7px`).
   - ❌ **NEVER** use unapproved border-radius values.
   - ✅ **ALWAYS** resolve visual values to `tokens/tokens.json` or CSS variables (`var(--ach-*)`).

2. **Reuse Before Invention**:
   - ❌ **DO NOT** invent new components or layout structures if one exists in `components/`, `patterns/`, or `templates/`.
   - ✅ **ALWAYS** check `components/_index.md` and `patterns/patterns.md` first.

3. **Strict Layering Protocol**:
   - **Tokens** (`tokens/`): Raw design values only. Never put layout or behavior logic here.
   - **Foundations** (`foundations/`): Rules for combining tokens (contrast, typography scale, spacing).
   - **Components** (`components/`): Atomic, reusable UI primitives. Never encode entire business flows here.
   - **Patterns** (`patterns/`): Layouts composed of components (e.g., TopBar, BottomActionBar).
   - **Templates** (`templates/`): Full page/modal screen flows composed of patterns and components.
   - **Business Context** (`business-context/`): Voice, terminology, legal disclaimers, and unit rules.

4. **Tone & Copy Constraints**:
   - ✅ **ALWAYS** consult `context/brand-voice.md` before writing labels, button text, error messages, or modal titles.
   - ❌ **NEVER** use informal filler ("Oops!", "Awesome!", "Let's do this!"). Keep it calm, direct, and professional.

---

## 2. Agent Decision Tree (How to Process Requests)

When a prompt or task is given, determine the scope and follow the path:

```mermaid
flowchart TD
    Prompt[User Prompt / UI Task] --> Type{Task Type?}
    
    Type -->|Single Element / Control| Comp[1. Read components/{name}.component.md]
    Type -->|Layout / Compound UI| Patt[2. Read patterns/{name}.pattern.md]
    Type -->|Full Page / Wizard / Flow| Temp[3. Read templates/{name}.template.md]
    Type -->|Styling / Theme Question| Tok[4. Read tokens/tokens.json & foundations/]
    
    Comp --> Tokens[Map styles to tokens.json / tokens.css]
    Patt --> Tokens
    Temp --> Tokens
    
    Tokens --> Copy[Verify copy against context/brand-voice.md]
    Copy --> Output[Generate Code Contract & Markup]
```

---

## 3. Token Resolution Matrix

When writing HTML, JSX, CSS, or Tailwind, map tokens as follows:

| Design System Token | CSS Custom Property | Tailwind Class (if configured) | Value Purpose |
| :--- | :--- | :--- | :--- |
| `color.brand.500` | `var(--ach-color-brand-500)` | `bg-ach-brand-500` / `text-ach-brand-500` | Primary interactive elements |
| `color.brand.600` | `var(--ach-color-brand-600)` | `bg-ach-brand-600` | Hover / active state on primary |
| `color.neutral.900`| `var(--ach-color-neutral-900)` | `text-ach-neutral-900` | Primary text and headings |
| `color.neutral.600`| `var(--ach-color-neutral-600)` | `text-ach-neutral-600` | Secondary / helper text |
| `color.neutral.200`| `var(--ach-color-neutral-200)` | `border-ach-neutral-200` | Standard borders and dividers |
| `color.neutral.50` | `var(--ach-color-neutral-50)` | `bg-ach-neutral-50` | Page / surface background |
| `color.neutral.0`  | `var(--ach-color-neutral-0)` | `bg-ach-neutral-0` | White card surfaces, button text |
| `color.feedback.danger` | `var(--ach-color-feedback-danger)` | `text-ach-feedback-danger` | Form error states & destructive actions |
| `space.16` | `var(--ach-space-16)` | `p-4` / `gap-4` (16px) | Standard content spacing |
| `space.12` | `var(--ach-space-12)` | `p-3` / `gap-3` (12px) | Compact padding |
| `radius.md` | `var(--ach-radius-md)` | `rounded-ach-md` (8px) | Buttons, inputs, modal cards |

*(Full token dictionary: [`tokens/tokens.json`](tokens/tokens.json))*.

---

## 4. Required Component States

Whenever an agent generates or modifies an interactive component (Button, Input, Dropdown, etc.), you **MUST** account for all 6 states:

1. **Default**: Normal resting appearance.
2. **Hover**: Subtly darkened or highlighted surface (`color.brand.600` for primary button).
3. **Pressed / Active**: Tactile feedback.
4. **Focus**: Visible focus ring conforming to WCAG 2.1 AA (`foundations/accessibility.md`).
5. **Disabled**: Visibly muted, non-interactive (`cursor: not-allowed`), **accompanied by an explanation/helper text** if reason is non-obvious.
6. **Loading**: Stable width/height with spinner or skeleton; prevents duplicate submissions.

---

## 5. Design Taste & Anti-Slop Directives

Agents must enforce the **Anti-Slop Enterprise Standard** ([`foundations/taste.md`](foundations/taste.md) / [`.agents/skills/ach-taste/SKILL.md`](.agents/skills/ach-taste/SKILL.md)):

1. **Mandatory Design Read**: State your one-line read before generating code:
   `"ACH Design Read: <Product Pilar> | <Surface Category> | Dials: [Density: X, Friction: Y, Motion: Z] | Target: <Persona>"`
2. **Kill Generic Card Syndrome**: Do not wrap every field or metric in a white card. Use whitespace, subtle borders (`border-ach-neutral-200`), and canvas background (`bg-ach-neutral-50`).
3. **Tabular Figures for Numbers**: All financial amounts, tax numbers, and metrics must use `font-variant-numeric: tabular-nums` or `font-mono`.
4. **Absolute Em-Dash Ban**: Never use `—` anywhere in UI copy. Use periods, commas, or simple hyphens (`-`).
5. **No AI Purple Glows or Decorative Motion**: Use only verified ACH brand tokens (`color.brand.500`). Zero unmotivated animations in data-entry flows.

---

## 6. Self-Correction & Verification Checklist

Before presenting UI code to the user, run this self-audit:

- [ ] **Design Read Stated**: Did I declare the one-line `ACH Design Read`?
- [ ] **Zero Hardcoded Styles**: Are there any `#hex` colors or arbitrary pixel values? (Must be `var(--ach-*)`).
- [ ] **Tabular Figures**: Are numeric columns, currency, and metrics styled with `tabular-nums`?
- [ ] **Single Primary Action**: Does the screen have at most ONE primary button?
- [ ] **No Generic Card Overload**: Is content grouped cleanly without wrapping everything in nested shadow cards?
- [ ] **Zero Em-Dash Violations**: Is visible text completely free of `—`?
- [ ] **Consistent Verbs**: Are button labels using standard action verbs ("Continue", "Save changes", "Review") instead of non-standard ones ("Next", "Submit")?
- [ ] **Accessibility & Error Recovery**: Do inputs have `<label>`, and do error messages explain how to fix the issue?
