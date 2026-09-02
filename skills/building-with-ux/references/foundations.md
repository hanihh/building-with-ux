# Pillar 1 — Foundations

**Default impact:** CRITICAL
**Rule prefixes:** `principles-`

The heuristics that govern every other pillar — visual hierarchy, consistency, feedback, affordance, recognition over recall, and managing cognitive load.

## Agent checklist

- [ ] Define the user, platform, task, primary job, supporting jobs, and independent decision regions.
- [ ] Choose one evidence-backed primary action in each decision region only when one action genuinely dominates.
- [ ] Prefer familiar patterns and validate the complete flow with realistic content and edge cases.

## Instructions

### Give each decision region one primary action

- **Rule ID:** `principles-one-primary-action`
- **Impact:** HIGH
- **Impact rationale:** Equal emphasis forces users to compare actions that should already be prioritized.
- **Impact summary:** clear priority reduces decision time
- **Tags:** hierarchy, actions, cognitive-load
- **Source:** "Memorisely — ‘Not every action needs to be a primary button’ (https://www.facebook.com/reel/720532684196196), date unknown"

Choose priority from the user's current goal, task sequence, frequency, and risk—not from visual taste. Give each decision region a dominant action when one genuinely dominates; independent regions may have different primaries. If evidence does not support a dominant action, use balanced secondary actions instead of inventing one. An informational region may need no action at all; never add a call to action merely to satisfy this rule. Demote low-value actions and reveal infrequent options progressively.

**Don't:** Six equally prominent buttons competing for attention.

**Do:** One evidence-backed primary in the current decision region, a small set of secondary actions, and a neutral **More** control for infrequent options.

### Prefer familiar interactions over novel ones

- **Rule ID:** `principles-use-familiar-interactions`
- **Impact:** HIGH
- **Impact rationale:** Familiar patterns reduce learning cost and keep users in flow.
- **Impact summary:** recognition is faster than learning
- **Tags:** familiarity, patterns, cognitive-load
- **Source:** "Memorisely — ‘The real takeaway for designers’ (https://www.facebook.com/reel/864213469477269), date unknown"

Reuse the platform and product patterns users already know unless research shows that a new interaction performs better. Novelty must earn its learning and accessibility cost.

**Don't:** Invent a new gesture for a common action only to make the interface feel distinctive.

**Do:** Use the expected gesture or control, then express personality through content and visual treatment.

### Validate with real content and complete flows

- **Rule ID:** `principles-validate-real-content-and-flows`
- **Impact:** HIGH
- **Impact rationale:** Placeholder-only happy paths conceal navigation, hierarchy, and state failures.
- **Impact summary:** functional constraints expose design problems early
- **Tags:** validation, content, prototyping, states
- **Source:** "Memorisely — ‘Save this if you’re tired of designs that only look good on Dribbble’ (https://www.facebook.com/reel/752424264177675), date unknown"

Use realistic names, dates, lengths, statuses, and data. Exercise navigation, search, unread/selected states, empty and error cases, alternate themes, and the path back—not only a polished happy-path frame.

**Don't:** Repeat idealized placeholder rows and judge the screen only as a static composition.

**Do:** Test short, long, missing, failed, selected, and localized content through the full task flow.
