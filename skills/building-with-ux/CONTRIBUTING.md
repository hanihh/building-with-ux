# Contributing: turning a talk into rules

This skill grows by distilling expert UX talks—Facebook or Instagram reels, YouTube videos,
conference talks, and articles—into **independently identifiable, sourced rules**. Rules live
as sections inside seven pillar references so the skill stays curated, traceable, and easy for
agents to load.

## Principles

- **One assertion per rule section.** A rule is a single, actionable claim, not a broad topic.
- **Source everything available.** Record creator, title, URL or platform, and date when known.
  Existing rules without a source remain valid records; do not invent provenance.
- **Curate, do not dump.** Most short talks contain hooks, stories, and repetition. Expect 1–4
  keepable rules, sometimes zero.
- **Generalize.** Keep the reusable principle. Retain a creator's specific example only when it
  makes the clearest Don't/Do pair.
- **Preserve stable IDs.** Existing IDs are citations and must not change during editing or
  consolidation unless the underlying rule changes identity.
- **Avoid duplicates.** Search titles, IDs, tags, and rule bodies before adding knowledge.

## Process checklist

### 1. Capture the source

- [ ] Transcribe or paste the spoken or written content into scratch work.
- [ ] Record the source URL, creator, title, and date when known.
- [ ] Do not commit the raw transcript unless it is itself a project deliverable.

### 2. Extract candidate claims

- [ ] List every distinct, actionable design assertion as an imperative.
- [ ] Ignore introductions, promotion, filler, and restated points.
- [ ] Separate compound advice into independently testable claims.

### 3. Filter and reconcile

Keep a claim only if it is:

- [ ] **Actionable** — an agent can check whether a design follows it.
- [ ] **Generalizable** — it applies beyond the source's single example.
- [ ] **Supported** — the rule does not overstate the source or invent technical detail.
- [ ] **New** — it is not already covered; otherwise improve the existing rule.

Drop unsupported taste, trend-chasing, and near-duplicates. If a new claim conflicts with an
existing rule, do not silently keep both:

- Prefer the more authoritative or current evidence when one clearly wins.
- When both apply in different contexts, add the condition to one rule.
- Preserve competing sources so the disagreement remains visible.

### 4. Choose the pillar and stable ID

| Pillar reference | Prefix(es) | Use for |
|---|---|---|
| `references/foundations.md` | `principles-` | Cross-cutting hierarchy, consistency, affordance, feedback, cognitive load |
| `references/layout-hierarchy.md` | `layout-` | Space, order, grid, alignment, whitespace, containers, responsiveness |
| `references/visual-design.md` | `visual-` | Color, tokens, contrast, type, radii, elevation, icons, style |
| `references/interaction-motion.md` | `interaction-` | States, animation, transitions, gestures, confirmations |
| `references/navigation-ia.md` | `nav-` | Structure, wayfinding, menus, search, back behavior, deep links |
| `references/content-microcopy.md` | `errors-`, `states-`, `forms-`, `feedback-`, `onboarding-` | Interface text and state patterns |
| `references/accessibility.md` | `a11y-` | Contrast, input, keyboard, semantics, reflow, reduced motion |

Create a unique kebab-case ID such as `layout-rank-content-before-styling`. For Content &
Microcopy, place the rule under its matching category heading.

### 5. Write the rule section

Use this template inside the selected reference:

```markdown
### Short imperative rule title

- **Rule ID:** `prefix-short-slug`
- **Impact:** MEDIUM
- **Impact rationale:** The usability consequence of ignoring this rule.
- **Tags:** tag1, tag2
- **Source:** Creator — "Talk title" (URL or platform), YYYY-MM

One or two sentences explaining what to do and why it matters for the user.

**Don't:** A concrete bad example.

**Do:** A concrete good example.

Optional nuance, edge cases, implementation example, research basis, or verification checks.
```

Use `####` for rule titles inside the category subsections of
`references/content-microcopy.md`. Omit `Source` only when no reliable source exists; never
fabricate one.

### 6. Register and validate

- [ ] Add the rule section to exactly one pillar reference.
- [ ] Update that reference's agent checklist only if the new rule changes its essential
  workflow; do not restate every rule in the checklist.
- [ ] Update rule counts in `SKILL.md`, this file's companion `README.md`, and `metadata.json`.
- [ ] Confirm `SKILL.md` still links directly to all seven references.
- [ ] Search for duplicate rule IDs and require exactly one occurrence per rule.
- [ ] Validate every rule has a title, ID, impact, impact rationale, tags, and complete body.
- [ ] Run the skill validator and Markdown/link checks before committing.

## Distillation worksheet

Use this in scratch work, not in the committed skill:

| # | Claim (imperative) | Actionable? | General? | Supported? | New? | Pillar / ID | Keep? |
|---|---|---|---|---|---|---|---|
| 1 |  | y/n | y/n | y/n | y/n |  | y/n |
