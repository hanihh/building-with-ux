# Contributing: turning a talk into rules

This skill grows by distilling expert UX talks — Facebook/Instagram reels, YouTube videos,
conference talks, articles — into **atomic, sourced rules**. This guide is the repeatable
process. The goal is a skill that stays *curated and traceable*: every rule earns its place
and names where it came from.

## Principles

- **One rule per file.** A rule is a single, actionable assertion — not a topic.
- **Source everything.** Each rule records the talk it came from (`source:` frontmatter), so
  claims stay verifiable and you can revisit the original.
- **Curate, don't dump.** Most of a 60-second reel is hook, story, and filler. Expect 1–4
  keepable rules from a talk, sometimes zero.
- **Generalize.** Keep the principle, drop the creator's specific app/example unless it makes
  the best Don't/Do pair.

## Process

### 1. Capture the transcript

Transcribe or paste the talk's spoken content into a scratch file. Keep the source URL,
creator name, and date — you'll need them for the `source:` field.

### 2. Extract candidate claims

List every distinct, *actionable* design assertion the speaker makes. Phrase each as an
imperative ("Mark the primary action," not "primary actions are important"). Ignore intros,
self-promotion, and restated points.

### 3. Filter

Keep a claim only if it is:

- **Actionable** — you could check whether a screen follows it.
- **Generalizable** — true beyond the speaker's one example.
- **Not already covered** — search existing rules first; if it overlaps, refine the existing
  rule instead of adding a near-duplicate.

Drop opinion, taste calls, and trend-chasing unless they carry a reusable principle.

### 4. Place it in a pillar

Assign each kept claim to a pillar and pick the prefix (see `rules/_sections.md`):

| Pillar | Prefix | Use when the claim is about… |
|--------|--------|------------------------------|
| Foundations | `principles-` | a cross-cutting heuristic (hierarchy, consistency, cognitive load) |
| Layout & Hierarchy | `layout-` | space, grid, alignment, whitespace, responsiveness |
| Visual Design | `visual-` | color, type, elevation, icons, style |
| Interaction & Motion | `interaction-` | states, animation, gestures, touch targets |
| Navigation & IA | `nav-` | structure, wayfinding, search, back behavior |
| Content & Microcopy | `errors- states- forms- feedback- onboarding-` | interface text and message patterns |
| Accessibility & Inclusion | `a11y-` | contrast, keyboard, screen readers, reduced motion |

### 5. Write the rule

Copy `rules/_template.md` to `rules/{prefix}-{slug}.md`. Fill in:

- `title` — the imperative rule
- `impact` / `impactDescription` — see levels in `README.md`
- `tags` — a few keywords for retrieval
- `source` — `Creator — "Talk title" (URL/platform), YYYY-MM`
- A tight **Don't / Do** pair — concrete and copy-pasteable

### 6. Register the rule

- Add a one-line entry under the matching pillar in `SKILL.md` → **Quick Reference**.
- Expand the rule under its pillar in `AGENTS.md` (the hand-maintained compiled guide).

## Handling conflicts

If a new claim contradicts an existing rule, don't silently add both. Reconcile:

- If one source is more authoritative or recent, note the nuance in the surviving rule.
- If both hold in different contexts, fold the condition into the rule ("for X, do A; for Y, do B").
- Record competing sources in `source:` so the disagreement stays visible.

## Distillation worksheet (scratch, not committed)

| # | Claim (imperative) | Actionable? | General? | New? | Pillar / prefix | Keep? |
|---|--------------------|-------------|----------|------|-----------------|-------|
| 1 |                    | y/n         | y/n      | y/n  |                 | y/n   |

Work the table, then write files only for the `Keep = y` rows.
