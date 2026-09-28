---
name: ach-design-taste
description: Anti-slop design taste and engineering standard for complex enterprise product UI, financial workflows, high-density data tables, and dashboards across the Achilles ecosystem (OnlinePajak, Credor, Covia).
---

# ACH Design Taste: Anti-Slop Enterprise Product Standard

> **Scope**: High-density dashboards, multi-step compliance wizards, complex financial transactions, data grids, and platform hubs across the Achilles ecosystem.  
> **Core Principle**: Serious enterprise software is evaluated on **clarity, speed, reliability, and typographical precision** — never on decorative filler.

---

## 0. BRIEF INFERENCE: Read the Product Context

Before writing any code or tweaking UI layout, **read the room**. Generic AI output fails in enterprise software because it treats complex business tools like marketing landing pages.

### 0.A Read these 5 signals first
1. **Product Pilar**:
   - `OnlinePajak` (Tax compliance, legal precision, zero-discrepancy e-Faktur/e-Bupot).
   - `Credor` (Liquidity, transparent financing terms, AI credit risk profiles).
   - `Covia` (Market intelligence, regional commodity price index, supply chain visibility).
   - `Platform Hubs` (Transaction Hub invoicing, Document Hub e-Sign/e-Meterai).
2. **Surface Category**:
   - High-Volume Data Table / Reconciliation Grid
   - Multi-Step Workflow / Compliance Wizard
   - Analytical & Metrics Dashboard
   - Approval & Transactional Action (e.g. Disbursement, SPT Filing)
   - Configuration / Organization Settings
3. **Data Density Needs**: Does the user need to scan 100 invoice rows per page, or make a focused high-stakes approval?
4. **Primary Persona**: Corporate Tax Specialist, CFO, Procurement Director, SME Founder.
5. **Regulatory & Risk Level**: Irreversible legal action (e.g. Lapor SPT, transfer dana) vs non-destructive draft editing.

### 0.B Mandatory One-Line "ACH Design Read"
Before generating code, declare your design read in this exact format:
> **"ACH Design Read: `<Product Pilar>` | `<Surface Category>` | Dials: [Density: `<1-10>`, Friction: `<1-5>`, Motion: `<1-3>`] | Target: `<Persona>`"**

*Example Reads*:
- *"ACH Design Read: OnlinePajak | High-Volume Data Grid (e-Faktur PPN) | Dials: [Density: 9, Friction: 4, Motion: 1] | Target: Corporate Tax Specialist"*
- *"ACH Design Read: Credor | Loan Disbursement Approval Dialog | Dials: [Density: 4, Friction: 5, Motion: 2] | Target: CFO"*
- *"ACH Design Read: Covia | Regional Commodity Price Index & Trend Chart | Dials: [Density: 7, Friction: 2, Motion: 2] | Target: Procurement Director"*

---

## 1. THE THREE ENTERPRISE DIALS

Enterprise software requires dials tuned for operational throughput and risk mitigation, not artsy visual chaos.

* **`DATA_DENSITY` (1 - 10)**:
  - `1-3 (Spacious / Onboarding)`: 48px+ row heights, generous whitespace, introductory guides.
  - `4-6 (Standard Workflow)`: 40px inputs, standard cards, settings pages, form wizards.
  - `7-10 (Cockpit / High-Density Grid)`: 32px compact rows, tabular numbers, sticky column headers, dense data filters, minimal padding.
* **`DECISION_FRICTION` (1 - 5)**:
  - `1 (Frictionless)`: Search filters, table sorting, expanding details, view switches.
  - `3 (Standard Form)`: Validated input fields, draft saving, non-destructive state changes.
  - `5 (High-Stakes / Irreversible)`: Final tax submission to DJP, fund disbursement, batch deletion. **Requires 2-step explicit confirmation dialog with impact summary**.
* **`MOTION_RESTRAINT` (1 - 3)**:
  - `1 (Instantaneous / Zero Delay)`: Critical for data entry, table pagination, filter updates. Zero animation lag.
  - `2 (Micro-Feedback)`: 150ms subtle transitions for dropdown menus, drawer slide-outs, accordion toggles.
  - `3 (Choreographed Workflow)`: Step transition in multi-step onboarding wizard.

---

## 2. ENTERPRISE ANTI-SLOP DIRECTIVES (Bias Correction)

LLMs suffer from predictable clichés when building dashboards and forms. Override them with these strict engineering rules:

### 2.1 Kill "Generic Card Syndrome"
* ❌ **AI Tell**: Wrapping every metric, every form field, and every 2-line sentence in a standalone rounded white card with a drop shadow. The screen turns into an unreadable patchwork of boxes.
* ✅ **Enterprise Rule**: Group related content using **whitespace hierarchy, subtle 1px dividers (`border-ach-neutral-200`), and semantic surface backgrounds (`bg-ach-neutral-50` vs white)**. Cards are reserved strictly for standalone interactive entities (e.g. selectable plan options, independent summary widgets).

### 2.2 Financial & Numerical Precision
* ❌ **AI Tell**: Displaying currency and numbers in proportional sans-serif fonts where numbers wobble and misalign vertically.
* ✅ **Enterprise Rule**:
  - Always enforce **tabular numbers** on all numeric data: `font-variant-numeric: tabular-nums` or `font-mono`.
  - Format Rupiah strictly according to Indonesian standard: `Rp 15.000.000` (space after Rp, dot as thousands separator).
  - Right-align numeric columns in data tables; left-align text; center-align status badges.
  - In financial summaries, display negative balances clearly with parentheses or minus: `-Rp 2.500.000` with `text-ach-feedback-danger`.

### 2.3 The "Single Primary Action" Law
* ❌ **AI Tell**: Placing 3 or 4 bright blue primary buttons on the same page (e.g. "Save", "Export", "Filter", "Continue" all competing for attention).
* ✅ **Enterprise Rule**:
  - There is **strictly ONE primary action** per view or context (e.g. "Lapor SPT" or "Lanjutkan").
  - Supporting actions must be **Secondary** (neutral border, transparent/white fill) or **Tertiary** (text-only).
  - Destructive actions (e.g. "Batalkan Faktur", "Hapus Data") must use the `destructive` variant and never share visual parity with forward primary actions.

### 2.4 Data Tables & High-Density Feeds
* ❌ **AI Tell**: Static 5-row table with raw text and no operational tools.
* ✅ **Enterprise Rule for Data Grids (`DATA_DENSITY >= 7`)**:
  - **Sticky Header**: Table header remains visible during vertical scroll.
  - **Bulk Action Bar**: Appears floating or pinned above the table when 1 or more rows are selected (e.g. "3 faktur dipilih — [Setujui] [Unduh PDF]").
  - **Data Freshness**: Always show last sync timestamp (e.g. *"Diperbarui per 28 Sep 2026, 13:40 WIB"*).
  - **Actionable Empty State**: Never show a blank white box. Include:
    1. Neutral icon
    2. Clear title (*"Belum ada transaksi"* / *"Faktur tidak ditemukan"*)
    3. Remedial action (*"Buat faktur baru"* atau *"Reset filter pencarian"*).

### 2.5 Complex Multi-Step Wizards & High-Stakes Forms
* ❌ **AI Tell**: Centering long forms in the middle of the screen like a contact page, with no progress context.
* ✅ **Enterprise Rule**:
  - Use a 2-column or master-detail layout: Step body on the left/main pane, real-time sticky summary card on the right (e.g. Total PPN, Rincian Pinjaman, Bea Meterai).
  - **Preserve Data on Back**: Navigating back through a stepper MUST NEVER clear entered data.
  - **Explicit Validation on Blur/Submit**: Do not block user typing with premature inline red errors on every keystroke. Validate on `blur` or when "Continue" is clicked.
  - **Exit Protection**: If user attempts to navigate away from a dirty form with unsaved changes, trigger a warning dialog.

---

## 3. THE ENTERPRISE SLOP BLACKLIST (Zero-Tolerance Bans)

The following patterns fail review immediately and must be rewritten:

1. **NO Em-Dash (`—`) Slop**:
   - The em-dash is the #1 tell of LLM-generated text. Completely banned in headlines, labels, pills, buttons, and body copy. Use a period, comma, or simple hyphen (`-`).
2. **NO AI Purple/Blue Glows & Neon Accents**:
   - Do not use futuristic purple glows, ambient mesh gradients, or cyberpunk cyan accents. Use the verified ACH token palette: `color.brand.500` (`#1F4EA3`), `color.neutral.*`, and semantic feedback colors.
3. **NO Unexplained Disabled Buttons**:
   - Never render a disabled button without nearby helper text or a tooltip explaining **why** it is disabled and **how** to unblock it (e.g. *"Lengkapi NPWP lawan transaksi untuk melanjutkan"*).
4. **NO Distorted Chart Axes**:
   - In Covia commodity charts or Credor risk visualizations, never truncate the Y-axis deceptively or use non-linear scaling that exaggerates normal price fluctuations.
5. **NO Informal Marketing Filler**:
   - Banned in enterprise UI: *"Oops!"*, *"Awesome!"*, *"Let's do this!"*, *"Supercharge your business"*, *"Effortless tax filing"*.
   - Use direct, adult, professional copy: *"Gagal memuat data faktur"*, *"Faktur berhasil disetujui"*, *"Hitung dan lapor SPT"*.
6. **NO Raw Hex Codes or Arbitrary Pixels**:
   - Never write `#1F4EA3`, `padding: 13px`, or `rounded-[7px]`. Map 100% of styles to `var(--ach-*)` tokens.

---

## 4. CANONICAL CODE PATTERNS (Enterprise Primitives)

### 4.A High-Density Metric KPI Card (With Tabular Numbers)
```tsx
export function MetricCard({
  label,
  value,
  trend,
  trendDirection,
  helperText,
}: {
  label: string;
  value: string;
  trend?: string;
  trendDirection?: 'up' | 'down' | 'neutral';
  helperText?: string;
}) {
  return (
    <div className="p-4 bg-ach-neutral-0 border border-ach-neutral-200 rounded-ach-md flex flex-col justify-between">
      <span className="text-sm font-medium text-ach-neutral-600">{label}</span>
      <div className="mt-2 flex items-baseline justify-between">
        <span className="text-2xl font-semibold tracking-tight text-ach-neutral-900 tabular-nums">
          {value}
        </span>
        {trend && (
          <span
            className={`text-xs font-medium px-2 py-0.5 rounded-full tabular-nums ${
              trendDirection === 'up'
                ? 'bg-green-50 text-ach-feedback-success'
                : trendDirection === 'down'
                ? 'bg-red-50 text-ach-feedback-danger'
                : 'bg-ach-neutral-100 text-ach-neutral-600'
            }`}
          >
            {trend}
          </span>
        )}
      </div>
      {helperText && (
        <span className="mt-2 text-xs text-ach-neutral-600">{helperText}</span>
      )}
    </div>
  );
}
```

### 4.B Master-Detail Sticky Workflow Pattern (Wizard / Form)
```tsx
export function WizardLayout({
  stepper,
  formBody,
  summarySidebar,
}: {
  stepper: React.ReactNode;
  formBody: React.ReactNode;
  summarySidebar: React.ReactNode;
}) {
  return (
    <div className="min-h-screen bg-ach-neutral-50 flex flex-col">
      <header className="border-b border-ach-neutral-200 bg-ach-neutral-0 sticky top-0 z-30 px-6 py-4">
        {stepper}
      </header>
      <main className="flex-1 max-w-7xl w-full mx-auto p-6 grid grid-cols-1 lg:grid-cols-12 gap-6 items-start">
        {/* Main form: 8 columns */}
        <section className="lg:col-span-8 bg-ach-neutral-0 border border-ach-neutral-200 rounded-ach-md p-6">
          {formBody}
        </section>
        {/* Sticky summary sidebar: 4 columns */}
        <aside className="lg:col-span-4 sticky top-24 space-y-4">
          {summarySidebar}
        </aside>
      </main>
    </div>
  );
}
```

---

## 5. SELF-CORRECTION PRE-FLIGHT CHECKLIST

Before presenting frontend code or design specifications to the user, run this audit:

- [ ] **Design Read Outputted**: Did I state the one-line `ACH Design Read`?
- [ ] **Zero Hardcoded Styles**: Are all colors and spacings resolved to `--ach-*` tokens?
- [ ] **Tabular Numerics**: Are all financial amounts, tax rates, and quantities styled with `tabular-nums`?
- [ ] **Single Primary Action**: Does each screen context feature at most ONE prominent forward button?
- [ ] **Explicit State Accounting**: Are default, hover, active, focus, disabled (with reason), and loading handled?
- [ ] **Zero Em-Dash Violations**: Is the visible text completely free of `—`?
- [ ] **Actionable Empty/Error State**: Do error alerts and empty tables instruct the user on how to resolve the state?
