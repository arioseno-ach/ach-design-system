# Design Taste & Anti-Slop Foundation

> **Authority**: Core foundation guide for visual taste, operational efficiency, and anti-slop standards across all Achilles products (OnlinePajak, Credor, Covia, Transaction Hub, Document Hub).  
> **Agent Implementation**: See [`.agents/skills/ach-taste/SKILL.md`](../.agents/skills/ach-taste/SKILL.md).

---

## 1. Why "Taste" in Enterprise & Fintech Matters

Most automated or AI-generated design falls into predictable "slop": generic centered cards, gratuitous purple gradients, unmotivated animations, and informal filler copy. 

In enterprise financial and compliance software, **good taste means**:
1. **Typographical & Numerical Precision**: Currency, quantities, and dates align flawlessly; numbers never wobble or misalign.
2. **High Data Density without Clutter**: Users can scan dozens of invoices, tax rows, or commodity trends quickly without visual exhaustion.
3. **Calm, High-Trust Hierarchy**: Every pixel conveys certainty. The user is in control of multi-million Rupiah transactions and legal compliance.

---

## 2. The 3 Scalable Product Dials

Every screen or flow in the ACH Design System is calibrated using three dials:

```
┌─────────────────┐       ┌─────────────────┐       ┌─────────────────┐
│  DATA_DENSITY   │       │DECISION_FRICTION│       │ MOTION_RESTRAINT│
│   (Level 1-10)  │       │   (Level 1-5)   │       │   (Level 1-3)   │
└────────┬────────┘       └────────┬────────┘       └────────┬────────┘
         ▼                         ▼                         ▼
   Spacious (1-3)            Fluid (1-2)             Instant (1)
   Standard (4-6)            Standard Form (3)       Subtle Micro (2)
   Cockpit Grid (7-10)       High-Stakes / 2-Step (5)Choreographed (3)
```

| Dial | Level Range | Practical Application |
| :--- | :--- | :--- |
| **`DATA_DENSITY`** | `1 - 10` | • **1-3**: Onboarding, public portals, introductory guides.<br>• **4-6**: Standard settings, single-record edit forms, approval cards.<br>• **7-10**: High-volume e-Faktur grids, reconciliation tables, commodity price benchmarks. |
| **`DECISION_FRICTION`** | `1 - 5` | • **1-2**: Sorting, filtering, expanding drawers, previewing receipts.<br>• **3**: Validated form saving, draft creation.<br>• **5**: Final submission to DJP, loan disbursement, batch record deletion (requires 2-step confirmation dialog). |
| **`MOTION_RESTRAINT`** | `1 - 3` | • **1**: Instantaneous (0ms delay) for data entry, table paging, and filters.<br>• **2**: 150ms micro-transition for dropdowns, drawers, and modal backdrops.<br>• **3**: Step transition in multi-step wizard. |

---

## 3. Core Enterprise Directives

### 3.1 Eliminating "Generic Card Syndrome"
Avoid nesting every paragraph or metric in an isolated rounded card with drop shadows. In complex enterprise workflows, group related content using:
- **Spatial hierarchy** (`space.16`, `space.24`)
- **Subtle borders** (`color.neutral.200`)
- **Surface contrast** (`color.neutral.50` canvas vs `color.neutral.0` active workspace)

### 3.2 Tabular Numerics for Financial Data
Financial and statistical data must always use tabular figures (`tabular-nums`):
```css
.ach-financial-number {
  font-variant-numeric: tabular-nums;
  text-align: right;
}
```
*Always align decimal places and currency symbols cleanly in vertical columns.*

### 3.3 Strict Single Primary Action
Every screen context must feature **at most ONE primary action** (`color.brand.500`). All supporting actions must be secondary or tertiary. Destructive actions must never be styled as primary forward actions.

### 3.4 Explicit State Discipline
Every interactive control must explicitly account for all 6 states:
1. **Default**: Resting appearance.
2. **Hover**: 1-shade darker surface (`color.brand.600`).
3. **Active**: Tactile feedback.
4. **Focus**: Visible focus ring conforming to WCAG 2.1 AA.
5. **Disabled**: Muted visuals, with nearby explanatory text on how to unblock.
6. **Loading**: Replaces label with spinner while preserving fixed dimensions.

---

## 4. The Anti-Slop Blacklist

| Banned Cliché ❌ | Approved Standard ✅ | Reason |
| :--- | :--- | :--- |
| **Em-dashes (`—`)** | Period, comma, or simple hyphen (`-`) | Signature tell of AI-generated text. Banned across all UI copy. |
| **AI Purple / Cyan Glows** | Tokenized palette (`color.brand.500`, neutral slate) | Prevents gimmickry; enforces corporate trust. |
| **Competing Primary Buttons** | One primary button per view context | Eliminates cognitive overload and accidental submissions. |
| **Unexplained Disabled Buttons** | Disabled button + explanatory helper text | Prevents user frustration and blocked workflows. |
| **Fake Div Screenshots** | Real components, real images, or clean typography | Div-based "mock preview boxes" scream placeholder slop. |
| **Informal Filler Copy** | Calm, direct action verbs (*"Lapor SPT"*, *"Lanjutkan"*) | Financial and compliance software demands professionalism. |
| **Raw Hex / Pixel Values** | Design tokens (`var(--ach-*)`) | Enforces design system integrity. |
