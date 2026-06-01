# Building with UX

**Version 2.0.0**
June 2026

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

Knowledge is distilled into atomic, sourced rules from practitioner talks (videos, reels,
articles); see `CONTRIBUTING.md`. Pillars 1–5 and 7 are scaffolded and fill over time. Pillar 6
(Content & Microcopy) ships complete with 25 rules.

## Design stance (applies across pillars)

- Serve the screen's one job; cut everything that doesn't.
- Consistency over novelty; reuse patterns, tokens, and terminology already in the product.
- Make the primary action obvious and give every action clear feedback.
- Be clear before clever; specific, not vague. Calm, direct, friendly, professional.
- Never fabricate technical detail or backend behavior. If context is missing, state assumptions.

## Build Workflow

1. **Frame** — purpose, audience, platform, and the one job this screen must do.
2. **Foundations** (`principles-`) — clear hierarchy, one primary action, fewer choices.
3. **Structure** (`layout-`, `nav-`) — consistent grid and spacing; predictable navigation.
4. **Style** (`visual-`) — coherent color and type system; semantic tokens, not raw values.
5. **Interaction & Motion** (`interaction-`) — states for every element; purposeful motion; fast feedback.
6. **Content & Microcopy** (Pillar 6) — apply the rules below.
7. **Accessibility** (`a11y-`) — contrast, keyboard, labels, reduced-motion, color-not-only.
8. **Review** — run the Pre-Delivery Checklist; cut anything that doesn't serve the job.

---

## Table of Contents

1. [Foundations](#pillar-1--foundations) — **CRITICAL** *(scaffolded)*
2. [Layout & Hierarchy](#pillar-2--layout--hierarchy) — **HIGH** *(scaffolded)*
3. [Visual Design](#pillar-3--visual-design) — **HIGH** *(scaffolded)*
4. [Interaction & Motion](#pillar-4--interaction--motion) — **HIGH** *(scaffolded)*
5. [Navigation & IA](#pillar-5--navigation--ia) — **HIGH** *(scaffolded)*
6. [Content & Microcopy](#pillar-6--content--microcopy) — **HIGH**
   - 6.1 [Errors & Failures](#61-errors--failures) — **CRITICAL**
   - 6.2 [Empty & Loading States](#62-empty--loading-states) — **HIGH**
   - 6.3 [Forms & Input](#63-forms--input) — **HIGH**
   - 6.4 [Success & Feedback](#64-success--feedback) — **MEDIUM**
   - 6.5 [Onboarding & Help](#65-onboarding--help) — **MEDIUM**
7. [Accessibility & Inclusion](#pillar-7--accessibility--inclusion) — **CRITICAL** *(scaffolded)*

---

## Pillar 1 — Foundations

**Impact: CRITICAL**

The heuristics that govern every other pillar — visual hierarchy, consistency, feedback,
affordance, recognition over recall, and managing cognitive load.

*Scaffolded. Rules are distilled from sourced talks (see `CONTRIBUTING.md`); none recorded yet.*

---

## Pillar 2 — Layout & Hierarchy

**Impact: HIGH**

How space and structure guide the eye — grid, spacing rhythm, alignment, whitespace, focal
point, content priority, and responsive behavior.

*Scaffolded. Rules are distilled from sourced talks (see `CONTRIBUTING.md`); none recorded yet.*

---

## Pillar 3 — Visual Design

**Impact: HIGH**

The surface treatment — color systems and contrast, type scale and pairing, elevation and
shadow, iconography, and style consistency.

*Scaffolded. Rules are distilled from sourced talks (see `CONTRIBUTING.md`); none recorded yet.*

---

## Pillar 4 — Interaction & Motion

**Impact: HIGH**

How the interface responds — interaction states, affordances, animation timing and easing,
gestures, touch targets, and microinteractions.

*Scaffolded. Rules are distilled from sourced talks (see `CONTRIBUTING.md`); none recorded yet.*

---

## Pillar 5 — Navigation & IA

**Impact: HIGH**

How people move and orient — information architecture, wayfinding, menus, search, back
behavior, and deep linking.

*Scaffolded. Rules are distilled from sourced talks (see `CONTRIBUTING.md`); none recorded yet.*

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

*Scaffolded. Rules are distilled from sourced talks (see `CONTRIBUTING.md`); none recorded yet.*
