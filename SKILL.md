---
name: dashboard-design-patterns
description: Design dashboards with patterns, genres, tradeoffs, process.
version: 0.1.0
author: Moaaz Magdy (MMS-21), Hermes Agent
compatibility: "Claude Code, Codex, Cursor, Copilot, Gemini, OpenCode, Pi, Windsurf, Hermes"
license: MIT
platforms: [linux, macos, windows]
metadata:
  hermes:
    tags: [dashboard, design, visualization, ui, patterns, ux]
    related_skills: []
---

# Dashboard Design Patterns Skill

Source: dashboarddesignpatterns.github.io (Bach et al., "Dashboard Design Patterns", IEEE VIS 2022 / TVCG 2023). A practical catalog of dashboard design patterns, dashboard genres (types), design tradeoffs, high-level guidelines, and a staged design process. Use it to make deliberate, defensible dashboard design decisions instead of guessing.

Does not cover: Tableau/Power BI tooling tutorials, programming visualizations (d3.js), or certification.

## When to Use

Load this skill when the user:
- Is designing, reviewing, or refactoring a dashboard (web, BI, analytics, embedded).
- Asks how to lay out dashboard widgets, choose charts, structure pages, or use color.
- Needs to pick a dashboard genre (static, magazine, infographic, mini, analytic, repository).
- Is stuck on screen-space, page count, abstraction, or interactivity tradeoffs.
- Wants a checklist or staged process for dashboard design.
- Asks for dashboard design guidelines or best practices.

Don't use for: implementing chart code, data pipelines, or non-dashboard UI (use frontend/design skills instead).

## Prerequisites

None. Pure reference knowledge. Optional supplementary material: the paper (arxiv 2205.00757), VIS 2022 talk slides, coding sheet, and dashboard collection linked in `## References`.

## Quick Reference

### Data Information (what the dashboard shows)
- **Individual values** — single data points (e.g. most recent value); implies importance.
- **Derived values** — computed info (trends, KPIs); abstraction over raw data.
- **Filtered** — subset by simple rule (e.g. last 14 days).
- **Thresholds** — judgment labels (good/bad/neutral) via objective cutoffs; high abstraction.
- **Aggregated data** — many points collapsed into one (sum/mean); implies related values.
- **Detailed datasets** — raw multi-attribute data; low judgment, invites exploration.

### Meta Information (context/explanation)
- **Data source** — origin, collection/analysis method, tools, direct data access.
- **Disclaimer** — assumptions, limitations, missing/misleading-data caveats.
- **Data description** — high-level statement of what the dashboard shows.
- **Update information** — last updated date/time.
- **Annotations** — author-added highlights of specific points/changes.

### Visual Representations (how data is drawn)
- **Numbers** — large prominent single key values (absolute/proportion/unit).
- **Trend-arrows** — up/down/neutral (or finer slopes); often red/green; beside numbers/tables.
- **Pictograms** — symbols illustrating concepts; may or may not encode data.
- **Gauges & progress bars** — range/scale reps (semicircle, bar, thermometer); may mark critical ranges.
- **Signature Charts** — small axis-less sparkline-like trends for quick glance.
- **Detailed Charts** — full axes/ticks/values for precise reading.
- **Tables** — raw values in tabular form; key-value lists to multi-column; may include signature charts/trend-arrows/color heatmaps.
- **Text Lists** — non-quantitative textual tickers.

### Interactions
- **Exploration** — brushing/linking across views, detail-on-demand (tooltips/pop-ups).
- **Navigation** — tabs, links, navigation buttons (forward/back), animated transitions (slideshows). Constrained (sequence) or unconstrained (free).
- **Personalization** — add/remove/resize/reorder representations; bespoke configs.
- **Filter and Focus** — search fields, checkboxes, radios, range sliders to narrow data.

### Screenspace strategies
- **Screenfit** — all content visible at once, no interaction needed.
- **Overflow** — content exceeds screen; revealed by scrolling (single page).
- **Detail-on-demand** — reveal details on request (tooltips/pop-ups); saves space.
- **Parameterized** — user controls what's shown (filters, sliders, date pickers, switches).
- **Multiple page** — content across pages, one at a time; navigate via tabs/buttons/links.

### Page Structure
- **Single Page** — all on one page (screenfit or overflow).
- **Hierarchical** — pages in levels; drill down from abstract to detailed.
- **Parallel** — pages at same level, no hierarchy; unconstrained tab/link nav; visual consistency.
- **Open** — multiple pages with loose relationships.
- **Semantic** — pages follow real-world structure (e.g. org divisions).

### Page Layout (widget arrangement)
- **Open Layouts** — widgets of varied sizes aligned to a grid; no strong semantic by position; reorderable.
- **Table Layouts** — widgets in rows/columns with shared semantics; supports comparison and juxtaposition.
- **Stratified Layouts** — top-down importance: high-level info on top, detail below.
- **Grouped Layouts** — explicit visual grouping (dividers, whitespace, shaded regions) of related widgets.
- **Schematic Layouts** — widgets placed by external property (map/geography/spatial).

### Color schemes
- **Distinct** — unique colors/palettes per widget or data type.
- **Shared** — one palette across the whole dashboard (branding).
- **Data Encoding** — color encodes categories or scales.
- **Semantic** — color carries meaning (traffic light, green/red sentiment).
- **Emotive** — aesthetic/emotional response.

## Dashboard Genres (Types)

Two families.

**Curated dashboards** (selective, goal-driven, author-driven storytelling):
1. **Static** — non-interactive, flat structure; signature charts, trend arrows, numbers, open layout, screenfit. Rare now due to digital/interactive expectations and adaptive displays.
2. **Magazine** — news/media dashboards inside articles; visualizations, annotations, tables, table/grid layout, overflow; narrative text interleaved with charts; editorial upkeep needed.
3. **Infographic** — decorative embellishments + data; annotations, pictograms, open layout, overflow; often static snapshots; artistic, less suited to frequently changing data.
4. **Embedded Mini** — small dashboard embedded in apps/sites; flat structure, parameterized, navigation interactions; links to deeper dashboard.

**Data collection dashboards** (transmit large volumes; reader-driven):
5. **Analytic** — Faceted Analytic Display / Multiple Coordinated Views; full visualizations, tables; exploration, navigation, personalization, parameterization, tabs/links; animated transitions; avoids overflow (scrolling hurts comparison).
6. **Repository** — many charts on one site; overflow + tabs; meta info (source, descriptions, disclaimers, update info); numbers, visualizations, navigation; acts as landing page for large data collections.

## Design Tradeoffs

Four parameters, each increasable/decreasable:
1. **Screenspace** available (increase = bigger screen/overflow; decrease = mobile/embedded).
2. **Number of pages** content is spread across (increase = more pages; decrease = combine).
3. **Abstraction** of data/info (increase = aggregated/single/derived; decrease = more detail).
4. **Interactivity** to access info (increase = exploration/filter/personalization/nav; decrease = static).

Ideal: minimize all four. But data/info often too large. Tradeoff rule (stress metaphor): minimizing one parameter increases stress on the others; maximizing reduces stress. Minimizing one parameter requires increasing one or more of the others:
- Decrease screenspace → increase pages, or interactivity, or abstraction.
- Increase screenspace → can decrease pages/interactivity/abstraction.

Same mutual relationships hold among all four. You may increase a single other parameter, or split the load across multiple.

## High-Level Guidelines

(Not priority-ordered.)
1. Don't overwhelm viewers.
2. Avoid visual clutter.
3. Avoid poor visual design.
4. Carefully choose KPIs.
5. Align with existing workflows.
6. Don't add too much data.
7. Provide consistency.
8. Provide interaction affordances.
9. Manage complexity.
10. Organize charts symmetrically.
11. Group charts by attribute.
12. Order charts by time.
13. Balance data + space.
14. Increase information.
15. Avoid redundancy of information.
16. Show information, rather than data.
17. Design is an iterative process.
18. Context is very important.
19. State your meta data.
20. Use color carefully.

### Pattern-based guidelines
- Consider design tradeoffs (above).
- Where space allows, provide redundant/complementary views and abstraction levels (e.g. numbers + trend-arrows + signature charts; single/derived/threshold values for at-a-glance key points; abstract encodings may take more space to emphasize importance).
- For transparency, provide meta information (data source, disclaimers); use tooltips or multiple pages if space is constrained.
- Avoid overflow in analytic dashboards (use screenfit or multiple pages) to facilitate comparison.
- Minimize repetitive data via abstraction (emphasize key data) and parameterization (support personalization).
- Pick the dashboard genre suited to audience/needs; use its characteristic patterns as a design checklist.
- Keep a consistent color scheme across the whole dashboard (reuse colors for same data/value, or a dedicated distinguishable scheme per visualization).
- Choose a layout expressing widget relations: schema, grouping by type/task, table, or stratified (important info on top).

## Staged Design Process

Stages are a guide, not strict instructions; design is iterative.

### Stage 0: Clarify the context
- Audience: what they know about data/viz; think of real personas.
- Setting: screen type (desktop/mobile/wall), interactivity possible, time available, frequency of use.
- Tasks & decisions: what they decide, info needed, lookup vs compare vs analyze.
- Information needed: all data or only relevant? Most relevant?

### Stage 1: Data & Information
Clarify which info from the dataset matters for the task (Stage 0). Use Data Information patterns; decide abstraction level (more data vs less).

### Stage 2: Structure
Single page or multiple? If multiple, define page relationships and what goes together (don't fear duplicating info). Meaningful structure aids navigation and consistency.

### Stage 3: Visual Representations
Find encodings per page. Match data abstraction to encoding detail. Guidelines: redundant/complementary views where space allows; minimize repetitive data via abstraction + parameterization; consistent color scheme.

### Stage 4: Page Layout
Organize components into a meaningful structure reflecting relations and importance (e.g. parallel/table for similar info).

### Stage 5: Screenspace
Fit everything on one screen, or interactively reveal off-screen data. Guideline: avoid overflow in analytic dashboards (use screenfit/multiple pages).

### Stage 6: Interactivity
Support exploration, focus & filter, navigation, personalization. Minimize interaction: if solvable with little/no interaction, do that.

## Workshop (from the site)

Goals: learn guidelines; design dashboards as mockups/sketches; understand decisions/tradeoffs; make deliberate decisions and reflect; use tools like Figma/Miro; discuss with peers.

Not provided: Tableau/Power BI intros, programming viz, certificates.

Prerequisites: a data/topic idea; context (audience, how dashboard supports people, where seen/interacted); ~2h beyond sessions.

Schedule: two weeks (March 2022), 3 stages, sync check-ins + async (Slack/forum). Sign-up limited to 12, free.

Activities:
1. Dashboard genres — show examples; discuss likes/dislikes and audience.
2. Introduce general guidelines + tradeoffs.
3. Introduce design thinking (double diamond).
4. Worksheet 1 — Data, Use & Genres (15 min): list/describe data facets; audience knowledge; tasks/decisions/workflow context; device context; pick 1-3 genres; report.
5. Worksheet 2 — Structure patterns (10 min): single vs multiple pages; group info; pick one page to continue.
6. Worksheet 3 — Data & Representation patterns (15 min): abstraction level; visualization choices.
7. Worksheet 4 — Layout (10 min): pick layout; experiment with post-its.
8. Worksheet 5 — Screenspace & Interactivity (10 min): handle overflow; need for interaction and UI support.
9. Worksheet 6 — Final Mockup (15 min): detailed mockup; two versions if undecided.

Instructor outline: https://dashboarddesignpatterns.github.io/workshopoutline.html
Materials: workshop slides PDF, worksheets PDF, cheatsheets PDF (all patterns).

## Pitfalls / Common Mistakes

- Overwhelming viewers; visual clutter; poor visual design.
- Choosing KPIs carelessly; too much data.
- Ignoring context/audience/workflow; design is iterative.
- Using overflow in analytic dashboards (hurts comparison).
- Inconsistent color schemes; redundant info.
- Forgetting meta information (source, disclaimers, update info).
- Not minimizing interaction when a static solution works.
- Infographic style on frequently changing data (high upkeep).
- Magazine dashboards need ongoing editorial oversight.

## Verification

When applying this skill to a design, check:
- [ ] Audience, setting, tasks, info needs clarified (Stage 0).
- [ ] Abstraction level chosen and justified (Data Information).
- [ ] Genre selected and its characteristic patterns used as checklist.
- [ ] Page structure justified (single vs multi, relationship type).
- [ ] Visual encodings chosen per page; redundant/complementary views where space allows.
- [ ] Layout expresses widget relations and importance.
- [ ] Screenspace strategy chosen; overflow avoided for analytic dashboards.
- [ ] Interactivity minimized to what's needed.
- [ ] Color scheme consistent across dashboard.
- [ ] Meta information present (source, disclaimer, description, update info).
- [ ] Tradeoffs among the four parameters acknowledged and balanced.

## References

- Site: https://dashboarddesignpatterns.github.io/
- Paper: Bach, Freeman, Abdul-Rahman, Turkay, Khan, Fan, Chen, "Dashboard Design Patterns", IEEE VIS 2022 / TVCG 2023. https://arxiv.org/abs/2205.00757
- VIS 2022 presentation: https://github.com/dashboarddesignpatterns/dashboarddesignpatterns.github.io/files/9822937/Dashboard.Design.Patterns.VIS.2022.live.talk.pdf
- Coding sheet: https://docs.google.com/spreadsheets/d/1wAHzX6QDgVQ9EsAVkyDuSmFL6LnErg9uBeJMbJcjC4k/edit
- Dashboard collection: https://drive.google.com/drive/folders/1X9QhXElytlTrtRACUZd0_292je72l4MS
- Cheatsheet compact: https://github.com/dashboarddesignpatterns/dashboarddesignpatterns.github.io/raw/main/docs/assets/Cheatsheet-compact.png
- Cheatsheet vertical: https://github.com/dashboarddesignpatterns/dashboarddesignpatterns.github.io/raw/main/docs/assets/Cheatsheet-vertical.png
- Workshop outline: https://dashboarddesignpatterns.github.io/workshopoutline.html
- Team: Benjamin Bach (University of Edinburgh, main contact), Euan Freeman (Glasgow), Alfie Abdul-Rahman (King's College London), Cagatay Turkay (Warwick), Saiful Khan (Oxford), Phong H. Nguyen (Redsift), Yulei Fan (Oxford), Min Chen (Oxford).

