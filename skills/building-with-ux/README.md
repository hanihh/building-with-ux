# Building with UX

An agent skill for building clean, usable interfaces through 60 actionable UX rules grouped
into seven task-level references.

## Structure

```text
building-with-ux/
├── SKILL.md                  # Activation, routing, workflow, and delivery checklist
├── references/
│   ├── foundations.md       # 4 rules
│   ├── layout-hierarchy.md  # 9 rules
│   ├── visual-design.md     # 11 rules
│   ├── interaction-motion.md # 4 rules
│   ├── navigation-ia.md     # 3 rules
│   ├── content-microcopy.md # 27 rules
│   └── accessibility.md     # 2 rules
├── CONTRIBUTING.md          # Transcript-to-rule maintenance process
├── metadata.json            # Version, author, abstract, and key references
└── README.md                # This maintenance map
```

The seven references replace the previous 48-file rule directory and duplicated compiled
guide. No rule content was removed: each rule keeps its title, stable ID, impact, impact
rationale, tags, source when one existed, instructions, examples, notes, and checks.

## How agents use the skill

1. Load `SKILL.md` when the task affects an interface.
2. Read Foundations and every reference selected by the routing table.
3. Follow the non-negotiable workflow before styling or implementation.
4. Apply the checklists and complete rule bodies in the selected references.
5. Run the pre-delivery checklist and report applied rule IDs.

For a complete interface or design review, agents read all seven references.

## Pillars

| # | Pillar | Stable rule prefix(es) | Rules |
|---|---|---|---:|
| 1 | Foundations | `principles-` | 4 |
| 2 | Layout & Hierarchy | `layout-` | 9 |
| 3 | Visual Design | `visual-` | 11 |
| 4 | Interaction & Motion | `interaction-` | 4 |
| 5 | Navigation & IA | `nav-` | 3 |
| 6 | Content & Microcopy | `errors-`, `states-`, `forms-`, `feedback-`, `onboarding-` | 27 |
| 7 | Accessibility & Inclusion | `a11y-` | 2 |

## Maintaining the rules

Use [`CONTRIBUTING.md`](CONTRIBUTING.md) to extract, evaluate, place, write, and register new
knowledge. Add a rule as a new section in the appropriate reference; do not create another
atomic file or a compiled duplicate. Keep the stable prefix-based ID so agents can cite rules
precisely.

## Impact levels

- `CRITICAL` — ignoring it blocks the task, causes data loss, or excludes users
- `HIGH` — ignoring it creates significant friction or confusion
- `MEDIUM` — ignoring it harms polish or trust
- `LOW` — incremental refinement
