# Building with UX

**Version 3.0.0**
September 2026

> **Note:**
> This document is for agents and LLMs to follow when designing, building, or reviewing user
> interfaces. Humans may also find it useful, but the guidance is optimized for automated,
> consistent application by AI-assisted workflows.

---

## Abstract

Holistic UX design intelligence for building clean, usable UI artifacts. Guidance is organized
into **7 pillars** that together cover a whole interface — Foundations, Layout & Hierarchy,
Visual Design, Interaction & Motion, Navigation & IA, Content & Microcopy, and Accessibility &
Inclusion — and is applied through a build workflow that turns intent into a clean artifact.

Knowledge is distilled into atomic rules from practitioner talks (videos, reels, articles);
see `CONTRIBUTING.md`. This guide compiles 48 rules across all 7 pillars. The 23
Memorisely-derived additions record direct reel provenance in their rule files.

## Design stance (applies across pillars)

- Frame the screen's primary and legitimate supporting jobs; cut content with no owned role.
- Consistency over novelty; reuse patterns, tokens, and terminology already in the product.
- Make the evidence-backed primary action in each decision region obvious and give every action clear feedback.
- Be clear before clever; specific, not vague. Calm, direct, friendly, professional.
- Never fabricate technical detail or backend behavior. If context is missing, state assumptions.

## Build Workflow

1. **Frame** — purpose, audience, platform, primary job, supporting jobs, and decision regions.
2. **Foundations** (`principles-`) — clear hierarchy, evidence-backed priority per decision region, fewer choices.
3. **Structure** (`layout-`, `nav-`) — inventory inputs, select task-relevant facts, define the
   reading order, and group with proximity before adding surfaces. Every additional or internal
   boundary needs a distinct job such as relationship, state, elevation, interaction,
   readability, or emphasis. Preserve the meaning and accuracy of anything presented; do not
   invent unsupported content; keep navigation predictable.
4. **Style** (`visual-`) — coherent color and type system. For reusable or themed product UI,
   build color as `raw value → primitive → semantic role`, and consume semantic roles in
   components. Disposable prototypes may use local semantic variables.
5. **Interaction & Motion** (`interaction-`) — states for every element; purposeful motion; fast feedback.
6. **Content & Microcopy** (Pillar 6) — apply the rules below.
7. **Accessibility** (`a11y-`) — contrast, keyboard, labels, reduced-motion, color-not-only.
8. **Review** — run the Pre-Delivery Checklist; cut anything that doesn't serve the job.

---

## Table of Contents

1. [Foundations](#pillar-1--foundations) — **CRITICAL**
2. [Layout & Hierarchy](#pillar-2--layout--hierarchy) — **HIGH**
3. [Visual Design](#pillar-3--visual-design) — **HIGH**
4. [Interaction & Motion](#pillar-4--interaction--motion) — **HIGH**
5. [Navigation & IA](#pillar-5--navigation--ia) — **HIGH**
6. [Content & Microcopy](#pillar-6--content--microcopy) — **HIGH**
   - 6.1 [Errors & Failures](#61-errors--failures) — **CRITICAL**
   - 6.2 [Empty & Loading States](#62-empty--loading-states) — **HIGH**
   - 6.3 [Forms & Input](#63-forms--input) — **HIGH**
   - 6.4 [Success & Feedback](#64-success--feedback) — **MEDIUM**
   - 6.5 [Onboarding & Help](#65-onboarding--help) — **MEDIUM**
7. [Accessibility & Inclusion](#pillar-7--accessibility--inclusion) — **CRITICAL**

---

## Pillar 1 — Foundations

**Impact: CRITICAL**

The heuristics that govern every other pillar — visual hierarchy, consistency, feedback,
affordance, recognition over recall, and managing cognitive load.

#### Give each decision region one primary action

Choose priority from the user's current goal, task sequence, frequency, and risk—not visual
taste. Use one dominant action only when one genuinely dominates the decision region;
independent regions may differ. Otherwise use balanced secondary actions. An informational
region may need no action at all; never add a call to action merely to satisfy this rule.
Demote low-value actions and reveal infrequent options progressively.

**Don't:** Six equally prominent buttons competing for attention.

**Do:** One evidence-backed primary, a small secondary set, and **More** for infrequent options.

#### Prefer familiar interactions over novel ones

Reuse platform and product patterns users already know unless research shows that a new
interaction performs better. Novelty must earn its learning and accessibility cost.

**Don't:** Invent a new gesture for a common action only to feel distinctive.

**Do:** Use the expected control and express personality through content and visual treatment.

#### Validate with real content and complete flows

Use realistic names, dates, lengths, statuses, and data. Exercise navigation, search, alternate
themes, empty/error states, and the path back—not only a polished happy path.

**Don't:** Repeat idealized placeholders and judge only a static composition.

**Do:** Test short, long, missing, failed, selected, and localized content through the full flow.

---

## Pillar 2 — Layout & Hierarchy

**Impact: HIGH**

How space and structure guide the eye — grid, spacing rhythm, alignment, whitespace, focal
point, content priority, and responsive behavior.

#### Design the information hierarchy before styling

Do not blindly preserve the source data's order or give every item equal emphasis. Before
choosing a layout, inventory the available inputs, select the facts relevant to the user's
task, and rank them from the user's likely questions:

1. **Primary** — the outcome, object, or action the user came to understand or complete.
2. **Secondary** — facts needed to explain, compare, or act on the primary information.
3. **Tertiary** — supplementary context such as time, location, or provenance when it is not
   central to the current task.

These are importance levels, not fixed field categories or a fixed screen order. Identity,
location, or any other field may be primary when the user's task makes it central; context may
also appear first so the primary content is understandable. Cluster related items, choose an
intentional reading sequence, then express the ranking with placement, scale, weight,
contrast, and spacing. Within one decision region, prefer two or three clearly distinguishable
emphasis levels; if everything is prominent, nothing is.

Keep labels, values, status, and actions close to the content they describe. Space inside a
group must be visibly smaller than the space between groups. Use shared alignment and
repetition for facts users compare.

**Don't:** Make a generic activity title the largest element, spread related metrics and
metadata across the card, and style every value with the same weight because that is how the
API returned the fields.

**Do:** For an activity summary, group person and time as context; make the meaningful result
the focal point; align comparable metrics; place location with the map; accent a verified
achievement; and keep actions together after the content. Adapt this anatomy to the user's
task rather than treating it as a universal card template.

Before delivery, render the interface at its target size and check:

- **Five-second read:** Can someone identify what this is, the main result, and what they can do
  if an action is relevant?
- **Squint test:** When details blur, do the intended focal point and groups remain visible?
- **Truth:** Is every displayed fact accurate and traceable through any formatting,
  localization, conversion, or derivation? Did the design avoid inventing status, metrics,
  achievements, or backend behavior?

Research basis: [NN/g on visual hierarchy](https://www.nngroup.com/articles/visual-hierarchy-ux-definition/)
and [the proximity principle](https://www.nngroup.com/articles/gestalt-proximity/).

#### Use one dominant alignment keyline

Prefer a shared left edge for multi-line or dense content. Mix alignment only when the change
communicates a real relationship, such as a trailing value column.

**Don't:** Stack centered headings, descriptions, prices, and actions with different centers.

**Do:** Align content to one keyline and use proximity to connect labels, values, and actions.

#### Use whitespace before adding containers

Treat containment as a semantic signal, not a default layout technique. Every additional or
internal background, border, shadow, divider, or nested surface must communicate a distinct
relationship, state, elevation, interaction, readability need, or emphasis. A base canvas or
outer component surface may define the working region. If an inner boundary's job cannot be
named, remove it.

First attempt to form each group through proximity, alignment, typography, and whitespace.
Use a common surface when a boundary makes a genuinely separate region easier to understand,
or when it emphasizes an important region. Do not nest containers when the parent and child
boundaries communicate the same group. Do not use a divider where a deliberate spacing change
already makes the separation clear.

**Don't:** Put metrics in an outlined panel inside a profile card, add a divider below it, and
give the header another heavy block merely to make the layout feel structured.

**Do:** In a profile summary, keep the outer card as the component boundary, use one restrained
header surface if identity needs emphasis, let aligned metrics group through proximity, and
separate the action row with whitespace. Treat this as an example of the decision—not a fixed
profile-card template.

Before delivery, temporarily remove each inner boundary. If the layout becomes unclear, first
repair spacing, alignment, or typography. Restore the boundary only when it conveys meaning
that those lighter signals cannot communicate.

Research basis: [NN/g on common regions](https://www.nngroup.com/articles/common-region/)
and [visual hierarchy](https://www.nngroup.com/articles/visual-hierarchy-ux-definition/).

#### Use a consistent spacing scale

Choose a small base unit—commonly 4px—and derive gaps, padding, and control sizes from its
multiples. Adjust for platform conventions, density, typography, and touch requirements.

**Don't:** Eyeball unrelated values such as 7px, 13px, and 19px throughout one family.

**Do:** Use named spacing tokens and document justified exceptions.

#### Design mobile screens as scrollable flows

Use the viewport to test the initial experience, not as a fixed canvas that must contain
everything. Preserve readable content and design the complete scroll and sticky behavior.

**Don't:** Shrink type, controls, and spacing until the task fits inside one phone frame.

**Do:** Prioritize the first view and let lower-priority content follow in a deliberate sequence.

---

## Pillar 3 — Visual Design

**Impact: HIGH**

The surface treatment — color systems and contrast, type scale and pairing, elevation and
shadow, iconography, and style consistency.

#### Match nested radii to their padding

For uniformly padded nested rounded shapes, start with
`outer radius = inner radius + padding`. Verify optically for asymmetric padding.

**Don't:** Apply the same radius to a card and its inset image.

**Do:** Increase the outer radius by the inset so the visible gap follows the curve evenly.

#### Give every color a job

Begin with neutral backgrounds and surfaces. Add color for action, feedback, state, identity,
or data meaning, and remove it when it serves none of those purposes.

**Don't:** Color avatars, icons, navigation, cards, and headings independently for decoration.

**Do:** Use a neutral base, accessible primary accent, and small semantic feedback palette.

#### Build dark-mode depth with dark surfaces

Use the darkest tone for the recessed screen background and progressively lighter dark tones
for elevated surfaces. Subdue borders and saturated accents; pure black is optional.

**Don't:** Paste a light-mode card onto a dark background or outline every surface in white.

**Do:** Express elevation through restrained tonal steps and recheck every state in context.

#### Test typefaces at their real use sizes

Evaluate counters, x-height, ascenders, descenders, baseline, line height, numerals, kerning,
and weights using actual interface strings at target sizes.

**Don't:** Choose a font from one large alphabet sample.

**Do:** Micro-test labels, paragraphs, tables, numbers, long names, and multiple scripts.

#### Use one coherent icon family

Prefer an established accessible library that covers product needs and maps cleanly to code.
Define size, stroke, fill, alignment, and active-state rules before adding exceptions.

**Don't:** Mix unrelated solid, outline, duotone, and 3D icons in one navigation.

**Do:** Use one family for controls and reserve other styles for separate illustrative roles.

#### Layer primitive and semantic tokens

For reusable or themed product UI, build color in three layers: raw values such as `#ffffff`, ordered primitives such as
`gray/100`, and semantic aliases such as `color/background/fill` or
`color/text/secondary`. Raw values define primitives; semantic aliases reference primitives;
components consume semantic aliases.

Name semantic tokens by purpose and state—background, surface, text, border, action, success,
warning, error, disabled—not by the color they currently contain. Map light, dark, and
high-contrast themes by changing the semantic mapping instead of editing component styles.
Document the primitive scale direction because names such as `gray/100` do not have a universal
meaning. A token diagram proves the architecture, not the palette: use supplied brand or product
colors, or state assumptions, rather than inventing a full theme from one example swatch.

**Don't:** Apply hex values or primitive tokens such as `gray/100` directly throughout
components, or name a component token after its current appearance such as `lightGrayCard`.

**Do:** Map `raw value → primitive → semantic role`, then consume only the semantic role in
component design and code. Raw values belong in token definitions; exceptional data
visualization palettes should still expose semantic series roles.

```css
:root {
  --gray-100: #ffffff;
  --gray-900: #161616;
  --color-background-fill: var(--gray-100);
  --color-text-primary: var(--gray-900);
}

.card {
  background: var(--color-background-fill);
  color: var(--color-text-primary);
}

[data-theme="dark"] {
  --color-background-fill: var(--gray-900);
  --color-text-primary: var(--gray-100);
}
```

Before delivery, inspect component styles for raw color literals and direct primitive usage.
Move each occurrence into the token layers unless a documented technical constraint requires
an exception, such as `transparent`, `currentColor`, user/data-driven colors, or immutable
brand assets. Test every documented foreground/background and interaction-state combination
for contrast in each supported theme. For a disposable prototype, local semantic variables may
replace a full primitive scale, but do not scatter unexplained literals through component code.

---

## Pillar 4 — Interaction & Motion

**Impact: HIGH**

How the interface responds — interaction states, affordances, animation timing and easing,
gestures, touch targets, and microinteractions.

#### Choose transitions by the information relationship

Use context transitions when content changes inside stable structure, drill transitions between
hierarchy levels, and continuity when a shared element persists into the next state.

**Don't:** Apply one dissolve to tabs, list-to-detail navigation, and card expansion.

**Do:** Keep tabs stable, express hierarchy during drill-in, and morph a shared card into detail.

#### Animate according to visual hierarchy

Keep persistent controls stable or fade them subtly. Give primary changing content the clearest
movement and stagger secondary elements only when it clarifies sequence.

**Don't:** Move every control, label, and background with equal intensity.

**Do:** Animate the changed card or sheet, preserve orientation, and provide reduced motion.

#### State consequences in destructive confirmations

Inform rather than ask. Use a verb-plus-object title, state the consequence and reversibility,
label the destructive action directly, and provide **Cancel** plus a close path.

**Don't:** “Are you sure?” with **Yes** and **No**.

**Do:** “Delete folder” — “This permanently deletes 18 files.” **Delete** / **Cancel**.

#### Stabilize button widths in aligned groups

When primary buttons repeat in an aligned group, use a shared minimum width or stretch them to
the container while allowing long localized labels to grow or wrap safely.

**Don't:** Let short and long labels create erratic widths in one comparison row.

**Do:** Apply a shared minimum or container width, then test the longest supported label.

---

## Pillar 5 — Navigation & IA

**Impact: HIGH**

How people move and orient — information architecture, wayfinding, menus, search, back
behavior, and deep linking.

#### Preserve hierarchy when sidebars collapse

Left-align and prioritize navigation, group related items, and keep the primary set concise.
Provide hover, focus, and active states. Every collapsed item needs a programmatic accessible
name; tooltips are supplemental and never replace that name or a usable touch pattern.

**Don't:** Leave an undifferentiated icon column with no active state.

**Do:** Keep order stable and verify keyboard, touch, screen-reader, collapsed, and dark states.

#### Use visual anchors for fast repeated choices

Pair repeated options with meaningful icons, silhouettes, or thumbnails. Keep text labels for
clarity and accessibility; the anchor supports recognition rather than replacing meaning.

**Don't:** Present visually identical text blocks for recognizable categories.

**Do:** Pair each option with a stable shape and label so users can scan, recognize, then confirm.

---

## Pillar 6 — Content & Microcopy

**Impact: HIGH**

The interface's text and message patterns. **Voice:** clear before clever; specific, not vague;
calm, direct, friendly, professional; reuse the product's terminology; no blame, jargon, or
invisible failures; never fabricate technical detail.

### 6.1 Errors & Failures

**Impact: CRITICAL**

When an action fails, help users understand the problem and recover quickly without exposing
sensitive technical details.

#### Say what happened, why, and what to do next

Structure every error as `[What happened]. [Why, if known and safe]. [What to do next].`

**Don't:**

```text
Something went wrong.
```

**Do:**

```text
Your payment didn't go through. Your bank declined the charge. Try a different card or contact your bank.
```

#### Use plain language, not codes or stack traces

Describe the problem in everyday words. No raw codes, stack traces, internal names, or a
bare "Something went wrong."

**Don't:**

```text
Error 0x80070057: ERR_CONN_REFUSED at SyncService.flush()
```

**Do:**

```text
We couldn't sync your changes because we lost the connection. Check your internet and try again.
```

#### Keep a neutral, non-blaming tone

Describe the situation without accusing the user. Focus on the state and the fix.

**Don't:**

```text
You entered an invalid email address.
```

**Do:**

```text
That email address doesn't look right. Check for typos and try again.
```

#### Always offer a realistic next step

Every error should point to something the user can actually do, and never give instructions
they can't follow.

**Don't:**

```text
This file can't be uploaded.
```

**Do:**

```text
This file is too large to upload. Choose a file under 25 MB.
```

#### Place errors where the problem is

Field errors next to the field; action failures inline near the trigger. Don't pile every
error at the top of a long page with no field highlights.

**Do:**

```text
Email
[ jane@ ]  ← Enter a valid email address.

[ Save ]
We couldn't save your changes. Try again.
```

#### Use modals only for must-resolve errors

Reserve blocking modals for problems the user must resolve before continuing, and always
include a primary action. Use inline messages for minor issues.

**Do:**

```text
[Modal] Payment didn't go through
Your card was declined. Update your payment method to complete your purchase.
[ Update payment ]
```

### 6.2 Empty & Loading States

**Impact: HIGH**

What users see when there's no data yet or while they wait. Set the right expectation and
offer a clear next step instead of a dead end.

#### Degrade gracefully — load and fail each section independently

**Impact: CRITICAL**

A page's parts come from different sources that load at different speeds and can fail on
their own. Render each section as soon as its own data is ready, and contain a section's
failure to that section so the rest of the page stays usable. Don't hold the whole page
behind one loading screen, and don't let one failed request become a full-page error.

**Don't:**

```text
[Whole page shows one spinner until profile, feed, and charts have all loaded]
[One failed request → the entire page is replaced by "Something went wrong"]
```

**Do:**

```text
[Stories render immediately; the feed shows a skeleton until it's ready]
[Sidebar is usable while the charts area shows its own loading state]
[If charts fail: that area shows "Couldn't load charts. Retry" — the rest of the page still works]
```

Like ordering delivery from three restaurants: eat what arrives instead of throwing it all
away because one order is late. Give each section its own loading state and its own inline,
retryable error.

#### Empty states explain purpose and offer a next step

Structure as `[What this area is for]. [Why it's empty]. [What to do next] + clear button.`

**Do:**

```text
No projects yet. Create your first project to start tracking work.
[ Create project ]
```

#### Don't let empty states become dead ends

Never a blank screen or blame; keep the tone encouraging and surface a way forward.

**Don't:**

```text
You haven't done anything yet.
```

**Do:**

```text
No results for "invoices 2025". Try a different keyword or adjust your filters.
```

#### Match the loading indicator to the scope of the wait

Skeleton for whole pages; progress bar for measurable uploads/downloads; inline spinner for
small actions; optimistic UI for low-stakes actions.

**Do:**

```text
[Skeleton cards in the dashboard layout] Loading your dashboard…
```

#### Show that progress is happening, especially for long waits

Communicate progress and what remains; tell users if they can leave and how they'll be
notified.

**Do:**

```text
Importing 120 contacts… 45% complete. You can leave this page; we'll email you when it's done.
```

#### Use optimistic UI only for low-stakes, reversible actions

Update immediately for easily reversible actions; revert and show an inline error on
failure. Don't use it for irreversible, high-stakes actions without confirmation.

**Do:**

```text
[Tap heart → fills immediately]
On failure: revert the heart, show "Couldn't save your like. Try again."
```

#### Show believable effort for complex work, never fake delays

Show brief, honest steps for genuinely complex operations; never add long fake delays to
simple actions.

**Do:**

```text
Comparing prices across airlines…
Reviewing your return for possible deductions…
```

### 6.3 Forms & Input

**Impact: HIGH**

Reduce friction so users can complete forms quickly and confidently, with feedback as soon
as something needs fixing.

#### Expose small choice sets instead of hiding them

For roughly two to seven mutually exclusive options, prefer radio buttons or a segmented
choice over a dropdown. For compact multi-select sets, use visible chips when practical and
keep selections visible.

**Don't:** Hide three choices or a multi-select list behind an abstract dropdown.

**Do:** Ask a clear question, show the choices, and visibly preserve what is selected.

#### Validate inline as users leave each field

Give feedback when the user leaves a field, not all at once after submit. Keep the message
under the field.

**Do:**

```text
Email
[ jane@example ]  ← Enter a valid email address.
```

#### Clearly mark required fields and what's missing

Mark required fields visibly and, if submit is disabled, show what still needs attention.

**Do:**

```text
Full name *   [ Jane Doe ]
Work email *  [          ]  ← Required
[ Submit ] (enabled once required fields are valid)
```

#### Show limits and rules up front, updating live

Show character limits and password rules before submit, updating as the user types.

**Do:**

```text
Password   [ ******** ]
✓ 8+ characters   ✓ a number   ✗ a capital letter

Bio   [ ... ]   120/160 characters
```

#### Pre-fill fields with data you already have

Pre-fill known values and keep them editable.

**Do:**

```text
Shipping to: Jane Doe, 12 Main St — prefilled from your account. [ Edit ]
```

#### Accept flexible input formats and normalize in the backend

Let users type natural formats; normalize server-side.

**Do:**

```text
Phone   [ 5551234567 ]   (also accepts 555-123-4567 or (555) 123-4567)
Stored as +1-555-123-4567
```

### 6.4 Success & Feedback

**Impact: MEDIUM**

Confirm that actions worked and surface status without interrupting the user's flow.

#### Confirm what succeeded, what's next, and a way forward

Structure as `[What succeeded]. [What happens next / where to find it]. [Optional action].`

**Do:**

```text
Your order is confirmed. We've emailed your receipt and tracking details.
[ View order ]
```

#### Use toasts only for low-importance, safe-to-miss updates

Don't put critical errors or required actions in a toast; don't stack overlapping toasts.

**Do:**

```text
[Toast] Saved as draft.
[Toast] You're back online. Syncing changes…
```

#### Use inline feedback when the user may need to act

Place actionable feedback inline near the related element, not in a disappearing toast.

**Do:**

```text
[Inline, under the table] 2 of 5 rows couldn't be imported. [ Review rows ]
```

#### Keep key information somewhere persistent

A transient message must never be the only place important info lives.

**Do:**

```text
[Toast] Export ready.
+ The export also appears in Downloads with a permanent link, and we email it to you.
```

### 6.5 Onboarding & Help

**Impact: MEDIUM**

Guide users to their first meaningful success without overwhelming them, and offer help
where questions naturally arise.

#### Focus onboarding on the few actions that lead to value

Guide toward the small number of actions that produce a first result, not a full tour.

**Do:**

```text
Create your first project to start organizing your work.
[ Create project ]
```

#### Offer short, context-specific help near complex controls

Put just-in-time help next to the control it explains; don't explain obvious UI.

**Do:**

```text
[Help icon next to "Results per page"] This controls how many results appear per page.
```

#### Always let users skip or dismiss onboarding

Let users skip, dismiss, or return later; keep tips short.

**Do:**

```text
Quick tip: drag tasks to reorder them.   [ Got it ]   [ Skip tips ]
```

---

## Pillar 7 — Accessibility & Inclusion

**Impact: CRITICAL**

Usable by everyone — color contrast, keyboard navigation, screen-reader semantics and labels,
reduced-motion, dynamic type, and never relying on color alone.

The two rules below come directly from the current transcript corpus; they are not a complete
accessibility standard. Keyboard behavior, focus order and visibility, screen-reader semantics,
dynamic type and reflow, reduced motion, color-not-only, and accessible charts and tables remain
baseline obligations. Apply current platform guidance and the WCAG level required by the product.

#### Test contrast in the real component context

Check text, icons, borders, focus indicators, disabled states, and action labels against their
actual surfaces in every theme. For web WCAG 2.2 AA, require 4.5:1 for normal text, 3:1 for
large text, and 3:1 for meaningful non-text UI boundaries or states.

**Don't:** Force the exact marketing swatch onto a primary button because it is canonical.

**Do:** Preserve the brand relationship while selecting a tested pair that passes the standard.

#### Give touch controls generous target areas

Size hit areas to platform guidance and center icons inside the larger target. For web WCAG 2.2
AA, require 24×24 CSS px or sufficient spacing under its exceptions; prefer 44×44 when space
allows. Test at text scaling and on a real device.

**Don't:** Make only the 20px icon tappable or overlap a floating action with tab targets.

**Do:** Make the full tab cell interactive, pair icon and label, and show a clear active state.

---

## Pre-Delivery Checklist

Before an artifact ships, confirm:

- **Foundations** — Each decision region has an evidence-backed primary when one genuinely
  dominates; the hierarchy guides the eye without flattening independent tasks.
- **Layout** — The rendered artifact has an intentional reading order and an appropriate number
  of distinguishable emphasis levels; related information is visibly grouped; spacing follows
  a consistent rhythm; nothing is arbitrarily aligned.
- **Surfaces** — Every additional or internal border, background, shadow, divider, and nested
  container communicates a distinct relationship, state, elevation, interaction, readability
  need, or emphasis; ordinary groups rely on proximity, alignment, typography, and whitespace.
  A base canvas or outer component surface may define the working region.
- **Visual** — Color and type come from one system; reusable or themed components consume
  semantic color tokens rather than raw values or primitives, except for documented technical
  constraints; no orphan styles.
- **Interaction** — Every interactive element has hover, press, disabled, and loading states;
  feedback is immediate.
- **Content** — Errors, empty/loading states, forms, and confirmations follow Pillar 6.
- **Accessibility** — Contrast passes in context, touch targets are generous, keyboard works,
  labels exist, color is not the only signal, and motion respects reduced-motion.
- **Fit** — Every element serves an identified primary or supporting job; unowned content is cut.
- **Reality** — Realistic content, edge states, themes, and the complete task flow have been exercised.
- **Visual read** — At target size, a five-second read and squint test reveal the intended focal
  point and groups; displayed information remains accurate and traceable through formatting,
  localization, conversion, or derivation; no unsupported content was invented.
