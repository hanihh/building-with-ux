---
name: building-with-ux
description: Holistic UX design intelligence for building clean, usable web and mobile interfaces. Use when designing, implementing, reviewing, or improving screens, components, flows, prototypes, landing pages, or dashboards. Covers information hierarchy, layout, surfaces, color systems and semantic tokens, typography, interaction, motion, navigation, content, microcopy, states, forms, and accessibility through seven focused references and a mandatory build-and-review checklist.
license: MIT
metadata:
  author: hani
  version: "4.1.0"
---

# Building with UX

Build interfaces that are understandable, purposeful, and usable—not merely decorated. This
skill contains **60 rules across 7 pillars**. The rules are consolidated by pillar so agents
can load complete, relevant guidance without navigating dozens of small files. The 35
Memorisely-derived rules retain direct reel provenance.

## When to apply

Use this skill whenever a task changes how an interface **looks, feels, reads, moves, or is
used**, including:

- Building a screen, component, flow, landing page, dashboard, prototype, or other UI artifact
- Reviewing or improving hierarchy, layout, usability, consistency, content, or accessibility
- Choosing visual treatment, interaction states, navigation behavior, feedback, or microcopy
- Diagnosing an interface that feels unclear, generic, cluttered, or unfinished

Skip it for pure backend, API, infrastructure, or non-interface work with no user-facing
visual or textual surface.

## Non-negotiable agent instructions

For every applicable task, follow this checklist in order:

- [ ] **Frame the job.** Identify the user, platform, task, primary job, supporting jobs,
  independent decision regions, constraints, and supplied information. When context is
  missing, state the assumptions that affect the design.
- [ ] **Select references before designing.** Read Foundations plus every pillar reference
  that affects the task. Never rely only on this summary when a relevant reference exists.
- [ ] **Inventory before styling.** Preserve the meaning and accuracy of supplied information;
  select what serves the task, rank it, group it, and establish reading order before visual
  styling. Never invent unsupported facts, states, metrics, achievements, or behavior.
- [ ] **Apply rules as instructions.** Treat relevant rule checklists and rule bodies as build
  requirements. Resolve conflicts using the user's task, platform conventions, evidence, and
  accessibility—not personal taste.
- [ ] **Render and inspect.** Evaluate the artifact at target size and in realistic content,
  edge, loading, empty, error, success, responsive, and theme states as applicable.
- [ ] **Run the pre-delivery checklist.** Fix failures before presenting the result. If a rule
  cannot be satisfied, name the rule, explain the constraint, and state the trade-off.
- [ ] **Report traceably.** Cite the applied pillar and rule IDs in the rationale and list the
  checks performed.

Do not flatten the interface into equally weighted information, preserve an accidental source
order, add decorative containers around every group, or introduce a primary action where the
task does not support one. The goal is an intentional hierarchy, not a fixed visual template.

## Reference routing

Read the smallest set that fully covers the task. Foundations is required for all interface
work; add every other affected pillar. For a complete interface or design review, read all
seven.

| # | Pillar | Read when the task involves | Reference |
|---|---|---|---|
| 1 | Foundations | Goals, hierarchy, priorities, familiar patterns, validation | [`references/foundations.md`](references/foundations.md) |
| 2 | Layout & Hierarchy | Information order, grouping, spacing, alignment, containers, grids, text length, responsive flow | [`references/layout-hierarchy.md`](references/layout-hierarchy.md) |
| 3 | Visual Design | Color, token and component naming, gradients, contrast, type scale, radii, elevation, icons, themes | [`references/visual-design.md`](references/visual-design.md) |
| 4 | Interaction & Motion | States, transitions, animation, confirmations, control stability | [`references/interaction-motion.md`](references/interaction-motion.md) |
| 5 | Navigation & IA | Structure, wayfinding, sidebars, tab bars, menus, repeated choices | [`references/navigation-ia.md`](references/navigation-ia.md) |
| 6 | Content & Microcopy | Errors, empty/loading states, forms, sign-up/login, feedback, onboarding, help | [`references/content-microcopy.md`](references/content-microcopy.md) |
| 7 | Accessibility & Inclusion | Contrast, touch, keyboard, semantics, reflow, reduced motion | [`references/accessibility.md`](references/accessibility.md) |

## Build workflow

1. **Frame** — Define the user, context, task, primary job, supporting jobs, independent
   decision regions, constraints, content inputs, and success criteria.
2. **Prioritize** — Apply Foundations. Give a decision region one primary action only when
   evidence shows one genuinely dominates; informational regions may need no action.
3. **Structure** — Apply Layout & Hierarchy and Navigation & IA. Inventory and rank supplied
   information, group related facts, create the reading order, and establish predictable
   navigation before styling.
4. **Style** — Apply Visual Design. Express hierarchy with placement, scale, weight, contrast,
   alignment, and spacing. Use proximity before containers. In reusable or themed product UI,
   use `raw value → primitive → semantic role → component`; components consume semantic roles.
5. **Make it respond** — Apply Interaction & Motion. Define states, communicate cause and
   effect, confirm destructive consequences, and provide immediate feedback.
6. **Write every state** — Apply Content & Microcopy. Cover default, empty, loading, error,
   success, forms, feedback, and onboarding where relevant.
7. **Include** — Apply Accessibility & Inclusion throughout implementation, not as a final
   cosmetic pass.
8. **Review** — Render the complete flow, run the checklist below, and remove anything that
   does not serve an identified job.

## Pre-delivery checklist

- [ ] **Foundations** — Each decision region has an evidence-backed primary only when one
  genuinely dominates; independent tasks are not flattened into one hierarchy.
- [ ] **Information** — The artifact preserves the meaning and accuracy of relevant supplied
  information. Formatting, localization, conversion, and derivation remain traceable. Nothing
  unsupported was invented.
- [ ] **Hierarchy** — The intended focal point, groups, and reading order are clear in a
  five-second read and squint test at target size. Two or three meaningful emphasis levels are
  distinguishable within a decision region.
- [ ] **Layout** — Related information is grouped; internal spacing is smaller than spacing
  between groups; spacing follows a consistent rhythm; alignment is intentional; responsive
  behavior forms a usable flow.
- [ ] **Surfaces** — Every additional or internal border, background, shadow, divider, and
  nested container communicates a distinct relationship, state, elevation, interaction,
  readability need, or emphasis. Ordinary groups use proximity, alignment, typography, and
  whitespace. A base canvas or outer component surface may define the working region.
- [ ] **Visual system** — Color, type, radii, elevation, and icons come from coherent systems.
  Reusable or themed components consume semantic color roles rather than raw values or
  primitives, except for documented technical constraints.
- [ ] **Interaction** — Applicable hover, focus, pressed, disabled, loading, success, and
  failure states exist; feedback is timely; motion explains relationships and respects reduced
  motion.
- [ ] **Content** — Errors, empty/loading states, forms, feedback, onboarding, and help follow
  Pillar 6; critical information persists instead of appearing only in transient UI.
- [ ] **Accessibility** — Contrast passes in context; touch targets are generous; keyboard
  paths and focus order work; accessible names and semantics exist; color is not the only
  signal; zoom, reflow, dynamic type, and reduced motion are supported as applicable.
- [ ] **Reality and fit** — Realistic content, edge states, themes, and the complete task flow
  were exercised. Every element serves an identified primary or supporting job; unowned
  content is removed.

## Required response format

When applying this skill, return:

1. **Artifact or recommendation** — the design, component, implementation, or change.
2. **Rule-based rationale** — concise reasoning tied to pillar names and rule IDs.
3. **Alternatives** — only when a meaningful trade-off needs a decision.
4. **Checks** — relevant pre-delivery checks run, failures fixed, and any unresolved constraint.

## Maintaining the skill

- Add or revise knowledge through [`CONTRIBUTING.md`](CONTRIBUTING.md).
- Keep each rule independently identifiable by its stable rule ID inside the appropriate pillar
  reference.
- Keep all seven reference links direct from this file; references must not depend on another
  file to locate their instructions.
