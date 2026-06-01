---
name: building-with-ux
description: Holistic UX design intelligence for building clean, usable UI artifacts on web and mobile. Use this skill when designing, building, reviewing, or improving any interface — covering visual hierarchy, layout, color, typography, interaction, motion, navigation, content and microcopy, and accessibility. Guidance is distilled into atomic, sourced rules across 7 pillars and applied through a build workflow that turns intent into a clean artifact. Triggers on building or refining UI (screens, components, flows, prototypes, artifacts) and on UX/design reviews.
license: MIT
metadata:
  author: hani
  version: "2.0.0"
---

# Building with UX

Design intelligence for building clean, usable interfaces. Guidance is organized into
**7 pillars** that together cover a whole interface — not just the words in it. Each rule is
atomic (one file), sourced from practitioner talks and references, and applied through a
**Build Workflow** that turns intent into a clean artifact.

> Knowledge in this skill grows by distilling expert UX talks (videos, reels, articles) into
> atomic rules. New pillars start empty and fill over time — see `CONTRIBUTING.md` for the
> transcript → rule process. The **Content & Microcopy** pillar ships with 25 rules.

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

Pillars 1–5 and 7 are scaffolded and populate as sources are transcribed. Pillar 6 is complete.

## Build Workflow

Apply the pillars in this order when building an artifact. Each step names the question to
answer; pull specific rules from the matching pillar's `rules/` as they exist.

1. **Frame** — What is this artifact for, who uses it, on what platform, and what is the one
   job this screen must do? Everything else serves that job.
2. **Foundations** (`principles-`) — Establish a clear hierarchy and one obvious primary
   action; remove choices that don't serve the job.
3. **Structure** (`layout-`, `nav-`) — Lay out on a consistent grid and spacing rhythm;
   prioritize core content; make navigation predictable.
4. **Style** (`visual-`) — Apply a coherent color system and type scale; prefer consistency
   over novelty; use semantic tokens, not raw values.
5. **Interaction & Motion** (`interaction-`) — Give every interactive element its states
   (hover/press/disabled/loading); use motion to explain cause and effect; confirm input fast.
6. **Content & Microcopy** (Pillar 6) — Apply the 25 rules below for errors, states, forms,
   feedback, and onboarding.
7. **Accessibility** (`a11y-`) — Verify contrast, keyboard paths, screen-reader labels,
   reduced-motion, and that color is never the only signal.
8. **Review** — Run the Pre-Delivery Checklist and cut anything that doesn't serve the job.

## Quick Reference

### Pillars 1–5, 7 (scaffolded)

No rules yet. As talks are transcribed, atomic rules land in `rules/{prefix}-{slug}.md` and
are listed here under their pillar. See `CONTRIBUTING.md` for the transcript → rule process.

### Pillar 6 — Content & Microcopy

**Voice:** clear before clever; specific, not vague; calm, direct, friendly, professional;
reuse the product's terminology; no blame, jargon, or invisible failures; never fabricate
technical detail.

#### Errors & Failures (`errors-`)

- `errors-what-why-next` — Structure errors as what happened, why, and what to do next
- `errors-plain-language` — No raw codes, stack traces, or "Something went wrong"
- `errors-no-blame` — Use a neutral, non-blaming tone
- `errors-actionable-recovery` — Always offer a realistic next step
- `errors-place-at-source` — Field errors by the field; action errors by the trigger
- `errors-modal-only-when-blocking` — Modals only for must-resolve issues, and include an action

#### Empty & Loading States (`states-`)

- `states-graceful-degradation` — Render what's ready; load and fail each section independently
- `states-empty-purpose-cta` — Empty states: what it's for, why it's empty, next step + CTA
- `states-empty-no-dead-end` — No blank screen, no blame; surface the primary action
- `states-loading-match-scope` — Match indicator to scope: skeleton, progress, spinner, optimistic
- `states-loading-set-expectations` — Show that progress is happening; communicate long waits
- `states-optimistic-safe-only` — Optimistic UI only for low-stakes reversible actions; revert on failure
- `states-labor-illusion-honest` — Show believable effort for complex work; never fake long delays

#### Forms & Input (`forms-`)

- `forms-inline-validation` — Validate inline as users leave each field, not all at once on submit
- `forms-mark-required` — Clearly mark required fields and show what's missing
- `forms-show-limits-and-rules` — Show character limits and password rules up front, updating live
- `forms-prefill-known-data` — Pre-fill fields with data you already have
- `forms-forgiving-input` — Accept flexible formats and normalize in the backend

#### Success & Feedback (`feedback-`)

- `feedback-confirm-success` — Confirm what succeeded, what's next, and a way forward
- `feedback-toasts-non-critical` — Use toasts only for low-importance, safe-to-miss updates
- `feedback-inline-when-actionable` — Use inline feedback near the element when the user may need to act
- `feedback-persist-critical-info` — Keep key information somewhere persistent, not only in a toast

#### Onboarding & Help (`onboarding-`)

- `onboarding-focus-key-actions` — Focus on the few actions that lead to value
- `onboarding-just-in-time-help` — Short, context-specific help near complex controls
- `onboarding-skippable` — Always allow skip/dismiss; no walls of text

## Pre-Delivery Checklist

Before an artifact ships, confirm:

- **Foundations** — There is one clear primary action; the hierarchy guides the eye to it.
- **Layout** — Spacing follows a consistent rhythm; nothing is arbitrarily aligned.
- **Visual** — Color and type come from one system; no orphan styles.
- **Interaction** — Every interactive element has hover/press/disabled/loading states; feedback is immediate.
- **Content** — Errors, empty/loading states, forms, and confirmations follow Pillar 6.
- **Accessibility** — Contrast passes, keyboard works, labels exist, color isn't the only signal, motion respects reduced-motion.
- **Fit** — Everything on screen serves the job; the rest is cut.

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
