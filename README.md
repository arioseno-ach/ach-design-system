# ACH Design System

**Status: ongoing.** The source of truth for ACH UI tokens, component contracts, interaction rules, and product language across OnlinePajak, Credor, Covia, Transaction Hub, and Document Hub.

## Start here

- Agents: read [`AGENTS.md`](./AGENTS.md).
- Engineers: read [`docs/integration-guide.md`](./docs/integration-guide.md).
- Tokens: use [`tokens/tokens.json`](./tokens/tokens.json) as source and [`tokens/tokens.css`](./tokens/tokens.css) as generated output.

## Use in another project

Add this repository as a submodule when your project needs the full documentation and agent context:

```bash
git submodule add https://github.com/arioseno-ach/ach-design-system.git docs/design-system
git submodule update --init --recursive
```

Import `docs/design-system/tokens/tokens.css` in the application stylesheet, then configure the agent to read `docs/design-system/AGENTS.md` before UI work.

## Structure

`tokens/` contains values. `foundations/` explains how to combine them. `components/` contains reusable contracts. `patterns/` contains reusable layouts and full-flow templates. `context/` defines product terminology and legal rules.

## Backlog

- [x] Set up agent-oriented repo structure with layered architecture.
- [x] Document business context for Achilles ecosystem, OnlinePajak, Credor, and Covia.
- [x] Add enterprise anti-slop taste standard and AI skill.
- [x] Create AGENTS.md operating manual for AI coding agents.
- [x] Write integration guide and Figma plugin PRD.
- [ ] Keep Figma Variables synchronized with [`tokens/tokens.json`](./tokens/tokens.json).
- [ ] Extract and review Figma components using [`components/_template.md`](./components/_template.md).
- [ ] Build the Figma plugin described in [`docs/archive/prd-figma-plugin.md`](./docs/archive/prd-figma-plugin.md), preferably in a dedicated plugin repository or issue.
- [ ] Promote draft components, patterns, and templates to stable after review.
