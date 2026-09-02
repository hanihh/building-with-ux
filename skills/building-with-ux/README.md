# Building with UX

A skill for AI agents that helps build clean, usable UI artifacts by applying UX design
guidance across a whole interface — structure, visuals, interaction, content, and accessibility.

Knowledge is distilled from expert UX talks (videos, reels, articles) into atomic rules. New
rules record direct provenance; see `CONTRIBUTING.md` for the transcript → rule process.

## Structure

- `SKILL.md` — entry point: pillars, build workflow, quick reference (loaded when the skill activates)
- `rules/` — one atomic rule per file, loaded on demand
  - `_sections.md` — pillar + section metadata (title, prefix, impact)
  - `_template.md` — template for creating new rules
  - `{prefix}-{slug}.md` — individual rule files
- `AGENTS.md` — full compiled guide (all rules expanded; what Codex and other agents read)
- `CONTRIBUTING.md` — how to turn a video/talk transcript into rules
- `metadata.json` — version, author, abstract

## Pillars (filename prefixes)

| # | Pillar | Prefix(es) | Status |
|---|--------|-----------|--------|
| 1 | Foundations | `principles-` | 3 rules |
| 2 | Layout & Hierarchy | `layout-` | 5 rules |
| 3 | Visual Design | `visual-` | 6 rules |
| 4 | Interaction & Motion | `interaction-` | 4 rules |
| 5 | Navigation & IA | `nav-` | 2 rules |
| 6 | Content & Microcopy | `errors- states- forms- feedback- onboarding-` | 26 rules |
| 7 | Accessibility & Inclusion | `a11y-` | 2 rules |

The skill currently contains 48 rules across all 7 pillars. The 23 Memorisely-derived additions
record direct reel provenance.

## Creating a new rule

1. Copy `rules/_template.md` to `rules/{prefix}-{slug}.md` using the right pillar prefix.
2. Fill in the frontmatter (`title`, `impact`, `impactDescription`, `tags`, `source`) and Don't/Do examples.
3. Add a one-line entry under the matching pillar in `SKILL.md` → **Quick Reference**.
4. Add the rule to `AGENTS.md` under its pillar (this repo ships a hand-maintained compiled doc).

Full step-by-step for distilling a talk into rules: `CONTRIBUTING.md`.

## Rule file structure

```markdown
---
title: Short imperative rule title
impact: HIGH
impactDescription: The usability consequence of ignoring this
tags: layout, hierarchy
source: Creator name — "Talk title" (URL or platform), YYYY-MM
---

## Short imperative rule title

**Impact: HIGH (the usability consequence)**

One or two sentences on what to do and why.

**Don't:**

​```text
Bad example
​```

**Do:**

​```text
Good example
​```
```

## Impact levels

Used to prioritize guidance, not measure performance:

- `CRITICAL` — ignoring it blocks the task, causes data loss, or excludes users
- `HIGH` — significant friction or confusion
- `MEDIUM` — noticeable polish and trust
- `LOW` — incremental refinement
