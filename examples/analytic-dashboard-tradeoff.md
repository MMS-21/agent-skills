# Example: Applying the skill to an analytic dashboard

**Scenario:** You're building an analytic dashboard (data-collection family) showing monthly revenue, churn, and NPS across 12 regions. The first draft crams everything onto one long page with 24 charts and a lot of scrolling.

## Step 1 — Stage 0: Clarify the context (skill → Staged Design Process)

- **Audience:** regional managers; they compare regions and drill into one.
- **Setting:** desktop, ~30s per check, weekly.
- **Tasks:** compare regions, spot anomalies, drill into one region's detail.
- **Info needed:** all 12 regions at overview, full detail on demand.

## Step 2 — Pick the genre

The skill lists **Analytic** dashboards as Faceted Analytic Displays: full visualizations, exploration, navigation, personalization, parameterization, tabs/links; **avoids overflow** because scrolling hurts comparison.

So the genre checklist says: no overflow, use screenfit or multiple pages.

## Step 3 — Tradeoffs (the 4 parameters)

Current design: screenspace small (one page), pages = 1, abstraction low (24 detailed charts), interactivity low.

The skill's tradeoff rule: minimizing one parameter requires increasing others.

- Goal: **minimize screenspace** (fit on one screen for comparison) → must **increase pages** and/or **abstraction** and/or **interactivity**.
- Decision: increase pages (overview page + per-region detail page) and abstraction (signature charts + numbers on overview, detailed charts only on detail page). Keep interactivity for drill-down (navigation links).

## Step 4 — Data Information choices

- Overview page: **Derived values** (KPIs: total revenue, avg churn, NPS), **Numbers** + **Trend-arrows** + **Signature Charts** (at-a-glance).
- Detail page: **Detailed datasets** (full charts, tables) for the selected region.

## Step 5 — Layout

- Overview: **Stratified** (KPIs on top, region grid below) using a **Table Layout** (12 region cells for comparison).
- Detail: **Grouped** (revenue block, churn block, NPS block).

## Step 6 — Color

**Shared** palette across the dashboard for brand consistency; **Semantic** red/green for churn direction.

## Step 7 — Meta information

Add **Data source**, **Update information**, **Disclaimer** (data refresh cadence) on the overview footer.

## Result

- Before: 1 page, 24 charts, heavy scroll, hard to compare.
- After: 1 overview (screenfit, 12 region cells + KPIs) + 12 detail pages (hierarchical drill-down), consistent color, meta info present.

## Verification (skill checklist)

- [x] Audience/setting/tasks clarified
- [x] Abstraction chosen (derived on overview, detailed on demand)
- [x] Genre = Analytic; overflow avoided
- [x] Structure = hierarchical (overview → region detail)
- [x] Layout = stratified + table on overview; grouped on detail
- [x] Interactivity = navigation (drill-down), minimized elsewhere
- [x] Color consistent (shared + semantic)
- [x] Meta info present
- [x] Tradeoffs acknowledged (screenspace minimized via pages + abstraction)
