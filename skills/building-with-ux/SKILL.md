---
name: building-with-ux
description: Holistic UX design intelligence for building clean, usable UI artifacts on web and mobile. Use this skill when designing, building, reviewing, or improving any interface — covering visual hierarchy, layout, color, typography, interaction, motion, navigation, content and microcopy, and accessibility. Guidance is distilled into atomic, sourced rules across 7 pillars and applied through a build workflow that turns intent into a clean artifact. Triggers on building or refining UI (screens, components, flows, prototypes, artifacts) and on UX/design reviews.
license: MIT
metadata:
  author: hani
  version: "3.0.0"
---

# Building with UX

Design intelligence for building clean, usable interfaces. Guidance is organized into
**7 pillars** that together cover a whole interface — not just the words in it. Each rule is
atomic (one file) and applied through a **Build Workflow** that turns intent into a clean
artifact. The 23 Memorisely-derived additions record direct reel provenance.

> Knowledge in this skill grows by distilling expert UX talks (videos, reels, articles) into
> atomic rules. See `CONTRIBUTING.md` for the transcript → rule process. The skill currently
> ships with **48 rules across all 7 pillars**.

## When to Apply

Use this skill when the task changes how an interface **looks, feels, reads, moves, or is used**:

- Building a new artifact — a screen, component, flow, landing page, dashboard, or prototype
- Reviewing or improving existing UI for usability, hierarchy, consistency, or accessibility
- Choosing structure, layout, visual treatment, interaction states, or copy
- Diagnosing "this doesn't feel professional / clear / finished" problems

Skip for: pure backend/API/infra work, or non-interface logic with no visual or textual surface.

## The 7 Pillars

| # | Pillar | Prefix | Focus | Impact |
|---|--------|--------|-------|--------|
| 1 | Foundations | `principles-` | Hierarchy, consistency, feedback, affordance, cognitive load | CRITICAL |
| 2 | Layout & Hierarchy | `layout-` | Grid, spacing rhythm, alignment, whitespace, focal point, responsive | HIGH |
| 3 | Visual Design | `visual-` | Color & contrast, type scale & pairing, elevation, iconography | HIGH |
| 4 | Interaction & Motion | `interaction-` | States, affordances, animation, gestures, touch targets | HIGH |
| 5 | Navigation & IA | `nav-` | Structure, wayfinding, search, back behavior, deep linking | HIGH |
| 6 | Content & Microcopy | `errors- states- forms- feedback- onboarding-` | Interface text and message patterns | HIGH |
| 7 | Accessibility & Inclusion | `a11y-` | Contrast, keyboard, screen readers, reduced motion, color-not-only | CRITICAL |

## Build Workflow

Apply the pillars in this order when building an artifact. Each step names the question to
answer; pull specific rules from the matching pillar's `rules/` as they exist.

1. **Frame** — What is this artifact for, who uses it, on what platform, and what is its
   primary job? Record legitimate supporting jobs and independent decision regions instead of
   forcing a complex dashboard into one action.
2. **Foundations** (`principles-`) — Establish a clear hierarchy and an evidence-backed
   primary action in each decision region; remove choices that don't serve the job.
3. **Structure** (`layout-`, `nav-`) — Lay out on a consistent grid and spacing rhythm;
   prioritize core content; make navigation predictable.
4. **Style** (`visual-`) — Apply a coherent color system and type scale; prefer consistency
   over novelty; use semantic tokens, not raw values.
5. **Interaction & Motion** (`interaction-`) — Give every interactive element its states
   (hover/press/disabled/loading); use motion to explain cause and effect; confirm input fast.
6. **Content & Microcopy** (Pillar 6) — Apply the rules below for errors, states, forms,
   feedback, and onboarding.
7. **Accessibility** (`a11y-`) — Verify contrast, keyboard paths, screen-reader labels,
   reduced-motion, and that color is never the only signal.
8. **Review** — Run the Pre-Delivery Checklist and cut anything that doesn't serve the job.

## Quick Reference

### Pillar 1 — Foundations

- [`principles-one-primary-action`](rules/principles-one-primary-action.md) — Give each decision region one primary action
- [`principles-use-familiar-interactions`](rules/principles-use-familiar-interactions.md) — Prefer familiar interactions over novel ones
- [`principles-validate-real-content-and-flows`](rules/principles-validate-real-content-and-flows.md) — Validate with real content and complete flows

### Pillar 2 — Layout & Hierarchy

- [`layout-group-and-rank-content`](rules/layout-group-and-rank-content.md) — Group content before styling and rank the groups
- [`layout-use-one-alignment-keyline`](rules/layout-use-one-alignment-keyline.md) — Use one dominant alignment keyline
- [`layout-use-whitespace-before-containers`](rules/layout-use-whitespace-before-containers.md) — Use whitespace before adding containers
- [`layout-use-consistent-spacing-scale`](rules/layout-use-consistent-spacing-scale.md) — Use a consistent spacing scale
- [`layout-design-mobile-as-scrollable-flow`](rules/layout-design-mobile-as-scrollable-flow.md) — Design mobile screens as scrollable flows

### Pillar 3 — Visual Design

- [`visual-match-nested-radii-to-padding`](rules/visual-match-nested-radii-to-padding.md) — Match nested radii to their padding
- [`visual-give-color-a-job`](rules/visual-give-color-a-job.md) — Give every color a job
- [`visual-build-dark-mode-depth-with-surfaces`](rules/visual-build-dark-mode-depth-with-surfaces.md) — Build dark-mode depth with dark surfaces
- [`visual-test-typefaces-at-use-size`](rules/visual-test-typefaces-at-use-size.md) — Test typefaces at their real use sizes
- [`visual-use-one-icon-family`](rules/visual-use-one-icon-family.md) — Use one coherent icon family
- [`visual-layer-primitive-and-semantic-tokens`](rules/visual-layer-primitive-and-semantic-tokens.md) — Layer primitive and semantic tokens

### Pillar 4 — Interaction & Motion

- [`interaction-choose-transition-by-relationship`](rules/interaction-choose-transition-by-relationship.md) — Choose transitions by the information relationship
- [`interaction-animate-by-hierarchy`](rules/interaction-animate-by-hierarchy.md) — Animate according to visual hierarchy
- [`interaction-confirm-destructive-actions-with-consequences`](rules/interaction-confirm-destructive-actions-with-consequences.md) — State consequences in destructive confirmations
- [`interaction-stabilize-aligned-button-widths`](rules/interaction-stabilize-aligned-button-widths.md) — Stabilize button widths in aligned groups

### Pillar 5 — Navigation & IA

- [`nav-structure-collapsible-sidebars`](rules/nav-structure-collapsible-sidebars.md) — Preserve hierarchy when sidebars collapse
- [`nav-use-visual-anchors-for-fast-choices`](rules/nav-use-visual-anchors-for-fast-choices.md) — Use visual anchors for fast repeated choices

### Pillar 6 — Content & Microcopy

**Voice:** clear before clever; specific, not vague; calm, direct, friendly, professional;
reuse the product's terminology; no blame, jargon, or invisible failures; never fabricate
technical detail.

#### Errors & Failures (`errors-`)

- [`errors-what-why-next`](rules/errors-what-why-next.md) — Structure errors as what happened, why, and what to do next
- [`errors-plain-language`](rules/errors-plain-language.md) — No raw codes, stack traces, or "Something went wrong"
- [`errors-no-blame`](rules/errors-no-blame.md) — Use a neutral, non-blaming tone
- [`errors-actionable-recovery`](rules/errors-actionable-recovery.md) — Always offer a realistic next step
- [`errors-place-at-source`](rules/errors-place-at-source.md) — Field errors by the field; action errors by the trigger
- [`errors-modal-only-when-blocking`](rules/errors-modal-only-when-blocking.md) — Modals only for must-resolve issues, and include an action

#### Empty & Loading States (`states-`)

- [`states-graceful-degradation`](rules/states-graceful-degradation.md) — Render what's ready; load and fail each section independently
- [`states-empty-purpose-cta`](rules/states-empty-purpose-cta.md) — Empty states: what it's for, why it's empty, next step + CTA
- [`states-empty-no-dead-end`](rules/states-empty-no-dead-end.md) — No blank screen, no blame; surface the primary action
- [`states-loading-match-scope`](rules/states-loading-match-scope.md) — Match indicator to scope: skeleton, progress, spinner, optimistic
- [`states-loading-set-expectations`](rules/states-loading-set-expectations.md) — Show that progress is happening; communicate long waits
- [`states-optimistic-safe-only`](rules/states-optimistic-safe-only.md) — Optimistic UI only for low-stakes reversible actions; revert on failure
- [`states-labor-illusion-honest`](rules/states-labor-illusion-honest.md) — Show believable effort for complex work; never fake long delays

#### Forms & Input (`forms-`)

- [`forms-expose-small-choice-sets`](rules/forms-expose-small-choice-sets.md) — Expose small choice sets instead of hiding them
- [`forms-inline-validation`](rules/forms-inline-validation.md) — Validate inline as users leave each field, not all at once on submit
- [`forms-mark-required`](rules/forms-mark-required.md) — Clearly mark required fields and show what's missing
- [`forms-show-limits-and-rules`](rules/forms-show-limits-and-rules.md) — Show character limits and password rules up front, updating live
- [`forms-prefill-known-data`](rules/forms-prefill-known-data.md) — Pre-fill fields with data you already have
- [`forms-forgiving-input`](rules/forms-forgiving-input.md) — Accept flexible formats and normalize in the backend

#### Success & Feedback (`feedback-`)

- [`feedback-confirm-success`](rules/feedback-confirm-success.md) — Confirm what succeeded, what's next, and a way forward
- [`feedback-toasts-non-critical`](rules/feedback-toasts-non-critical.md) — Use toasts only for low-importance, safe-to-miss updates
- [`feedback-inline-when-actionable`](rules/feedback-inline-when-actionable.md) — Use inline feedback near the element when the user may need to act
- [`feedback-persist-critical-info`](rules/feedback-persist-critical-info.md) — Keep key information somewhere persistent, not only in a toast

#### Onboarding & Help (`onboarding-`)

- [`onboarding-focus-key-actions`](rules/onboarding-focus-key-actions.md) — Focus on the few actions that lead to value
- [`onboarding-just-in-time-help`](rules/onboarding-just-in-time-help.md) — Short, context-specific help near complex controls
- [`onboarding-skippable`](rules/onboarding-skippable.md) — Always allow skip/dismiss; no walls of text

### Pillar 7 — Accessibility & Inclusion

- [`a11y-test-contrast-in-context`](rules/a11y-test-contrast-in-context.md) — Test contrast in the real component context
- [`a11y-size-touch-targets-generously`](rules/a11y-size-touch-targets-generously.md) — Give touch controls generous target areas

These two corpus-derived rules are additions, not a complete accessibility standard. Keyboard,
screen-reader semantics, focus order/visibility, dynamic type/reflow, reduced motion,
color-not-only, and accessible charts/tables remain baseline obligations. Apply the current
platform guidance and WCAG level required by the product even when no atomic rule exists yet.

## Pre-Delivery Checklist

Before an artifact ships, confirm:

- **Foundations** — Each decision region has an evidence-backed primary when one genuinely dominates; the hierarchy guides the eye without flattening independent tasks.
- **Layout** — Spacing follows a consistent rhythm; nothing is arbitrarily aligned.
- **Visual** — Color and type come from one system; no orphan styles.
- **Interaction** — Every interactive element has hover/press/disabled/loading states; feedback is immediate.
- **Content** — Errors, empty/loading states, forms, and confirmations follow Pillar 6.
- **Accessibility** — Contrast passes in context, touch targets are generous, keyboard works, labels exist, color isn't the only signal, and motion respects reduced-motion.
- **Fit** — Every element serves an identified primary or supporting job; unowned content is cut.
- **Reality** — Realistic content, edge states, themes, and the complete task flow have been exercised.

## Response Format

When applying this skill, structure outputs as:

1. **Artifact / Recommendation** — the design, component, or change.
2. **Rationale** — bullets tied to specific rules (cite rule names and pillars).
3. **Alternatives** (optional) — variants when a trade-off is worth surfacing.
4. **Checks** — the relevant Pre-Delivery Checklist items.

## How to Use

- Read individual rule files for detail and examples: `rules/{prefix}-{slug}.md`
- Add new knowledge from a talk: follow `CONTRIBUTING.md`
- Section map, prefixes, and impacts: `rules/_sections.md`
- Full compiled guide (all rules expanded): `AGENTS.md`
