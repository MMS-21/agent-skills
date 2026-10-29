# Agent Skills — Dashboard Design Patterns

A reusable **Agent Skill** that distills the [Dashboard Design Patterns](https://dashboarddesignpatterns.github.io/) research (Bach et al., IEEE VIS 2022 / TVCG 2023) into a practical playbook any coding agent can load.

**Skill name:** `dashboard-design-patterns`

## What it does

When your agent is designing, reviewing, or refactoring a dashboard, this skill gives it:

- A **catalog of design patterns** — Data Information, Meta Information, Visual Representations, Interactions, Screenspace, Page Structure, Page Layout, Color
- **6 dashboard genres** (Static, Magazine, Infographic, Embedded Mini, Analytic, Repository) with characteristic pattern checklists
- **Design tradeoffs** — the 4 parameters (screenspace, pages, abstraction, interactivity) and the stress metaphor
- **20 high-level guidelines** + pattern-based guidelines
- A **staged 7-step design process** (Stage 0 → 6)
- A **workshop worksheet flow**, common pitfalls, and a verification checklist

It does *not* cover Tableau/Power BI tutorials, programming visualizations (d3.js), or certification.

## Install

This skill follows the [Agent Skills open standard](https://agentskills.io/specification): a folder with a `SKILL.md` at its root. Clone it into the skills directory your agent reads.

### One-liner (any agent)

```bash
npx skills add MMS-21/agent-skills
```

### Manual per agent

| Agent | Global path | Project path |
|---|---|---|
| Claude Code | `~/.claude/skills/dashboard-design-patterns` | `.claude/skills/dashboard-design-patterns` |
| OpenAI Codex | `~/.codex/skills/dashboard-design-patterns` | `.codex/skills/dashboard-design-patterns` |
| Cursor | `~/.cursor/skills/dashboard-design-patterns` | `.cursor/skills/dashboard-design-patterns` |
| GitHub Copilot | `~/.copilot/skills/dashboard-design-patterns` | `.github/skills/dashboard-design-patterns` |
| Gemini CLI | `~/.gemini/skills/dashboard-design-patterns` | `.gemini/skills/dashboard-design-patterns` |
| OpenCode | `~/.config/opencode/skills/dashboard-design-patterns` | `.opencode/skills/dashboard-design-patterns` |
| Pi | `~/.pi/agent/skills/dashboard-design-patterns` | `.pi/skills/dashboard-design-patterns` |
| Windsurf | — (project only) | `.windsurf/skills/dashboard-design-patterns` |
| Hermes Agent | `~/.hermes/skills/dashboard-design-patterns` | — |

**Claude Code / Codex / Cursor / Copilot / Gemini / OpenCode / Pi** also read the shared interop path `~/.agents/skills/dashboard-design-patterns`, so a single clone there covers several at once.

Example (Claude Code, global):

```bash
git clone https://github.com/MMS-21/agent-skills ~/.claude/skills/dashboard-design-patterns
```

Example (shared interop, covers Codex + Cursor + Copilot + Gemini + OpenCode + Pi):

```bash
git clone https://github.com/MMS-21/agent-skills ~/.agents/skills/dashboard-design-patterns
```

Restart the agent (or start a new session) so it discovers the skill. In most agents you can invoke it explicitly by typing `/` and picking `dashboard-design-patterns`.

### ChatGPT (Custom GPT)

ChatGPT has no skills directory. To use this knowledge there:

1. Create a Custom GPT.
2. Paste the contents of `SKILL.md` into the **Instructions** field (trim the YAML frontmatter if you like).
3. Save and chat.

### Pi

Pi scans `.pi/skills/` and the shared `.agents/skills/` tree, so either path above works without duplication.

## Example: applying the skill

See [`examples/analytic-dashboard-tradeoff.md`](examples/analytic-dashboard-tradeoff.md) for a walkthrough turning an overflow-heavy analytic dashboard into a screenfit, multi-page design using the skill's tradeoff framework.

## Contents

```
agent-skills/
├── SKILL.md          # the skill (Agent Skills standard)
├── README.md         # this file
├── LICENSE           # MIT
├── examples/         # walkthroughs
├── references/       # supplementary notes
└── agents/
    └── openai.yaml   # Codex optional metadata
```

## Sources & attribution

- Site: https://dashboarddesignpatterns.github.io/
- Paper: Bach, Euan Freeman, Alfie Abdul-Rahman, Cagatay Turkay, Saiful Khan, Yulei Fan, Min Chen. *Dashboard Design Patterns*. IEEE VIS 2022 / IEEE TVCG 2023. https://arxiv.org/abs/2205.00757
- VIS 2022 talk, coding sheet, dashboard collection: see `SKILL.md` → References.

This skill is an independent distillation for educational/practical use; all credit for the patterns goes to the original authors.

## License

MIT — see [LICENSE](LICENSE).
