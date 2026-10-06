---
name: ach-design-taste
description: Use for enterprise product UI in the Achilles ecosystem, especially financial workflows, data grids, dashboards, and compliance flows.
---

# ACH design taste

Use this skill before creating or changing UI for OnlinePajak, Credor, Covia, Transaction Hub, or Document Hub.

1. Read [`foundations/taste.md`](../../../foundations/taste.md). It is the single source of truth for anti-slop directives, high-density grids, and high-stakes workflows.
2. Read the relevant product context in [`context/units/`](../../../context/units/).
3. State this line before generating UI code:

   `ACH Design Read: <Product Pilar> | <Surface Category> | Dials: [Density: <1-10>, Friction: <1-5>, Motion: <1-3>] | Target: <Persona>`

4. Apply the three dials:
   - Density: 1-10
   - Friction: 1-5
   - Motion: 1-3
5. Complete the anti-slop and component-state checks defined in `foundations/taste.md` and `AGENTS.md` before presenting UI work.
