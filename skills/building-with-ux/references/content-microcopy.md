# Pillar 6 — Content & Microcopy

**Default impact:** HIGH
**Rule prefixes:** `errors-`, `states-`, `forms-`, `feedback-`, `onboarding-`

The interface's text and message patterns across errors, empty and loading states, forms, feedback, onboarding, and help.

## Section map

| Section | Prefix | Surface | Default impact |
|---|---|---|---|
| Errors & Failures | `errors-` | Something went wrong | CRITICAL |
| Empty & Loading States | `states-` | No data yet / waiting | HIGH |
| Forms & Input | `forms-` | Collecting input | HIGH |
| Success & Feedback | `feedback-` | Confirming outcomes | MEDIUM |
| Onboarding & Help | `onboarding-` | First use / guidance | MEDIUM |

## Contents

- [Errors & Failures](#errors--failures)
- [Empty & Loading States](#empty--loading-states)
- [Forms & Input](#forms--input)
- [Success & Feedback](#success--feedback)
- [Onboarding & Help](#onboarding--help)

## Agent checklist

- [ ] Write clearly before cleverly: specific, calm, direct, friendly, professional, and consistent with product terminology.
- [ ] Explain failures without blame, place them at their source, and always offer a realistic recovery path.
- [ ] Make empty, loading, success, form, and onboarding states informative, actionable, and proportional to their importance.
- [ ] Never fabricate technical detail, hide critical information in a toast, or block progress without necessity.

## Instructions

### Errors & Failures

#### Say what happened, why, and what to do next

- **Rule ID:** `errors-what-why-next`
- **Impact:** CRITICAL
- **Impact rationale:** Users can't recover from errors they don't understand
- **Tags:** errors, recovery, structure

Structure every error as `[What happened]. [Why, if known and safe]. [What to do next].`
State what failed in plain language, add the cause when it's safe and helpful, and end
with a specific recovery action.

**Don't:**

```text
Something went wrong.
```

**Do:**

```text
Your payment didn't go through. Your bank declined the charge. Try a different card or contact your bank.
```

Keep it short and focused on recovery. Omit the "why" only when it isn't known or would
expose sensitive detail — never omit the "what to do next."

#### Use plain language, not codes or stack traces

- **Rule ID:** `errors-plain-language`
- **Impact:** HIGH
- **Impact rationale:** Technical dumps leave users stuck and erode trust
- **Tags:** errors, clarity, jargon

Describe the problem in everyday words. Don't expose raw error codes, stack traces, or
internal system names, and don't fall back to a vague "Something went wrong" with no
detail. If a support reference code is genuinely useful, keep it secondary to a plain
explanation.

**Don't:**

```text
Error 0x80070057: ERR_CONN_REFUSED at SyncService.flush()
```

**Do:**

```text
We couldn't sync your changes because we lost the connection. Check your internet and try again.
```

#### Keep a neutral, non-blaming tone

- **Rule ID:** `errors-no-blame`
- **Impact:** MEDIUM
- **Impact rationale:** Blame raises stress and makes recovery feel like punishment
- **Tags:** errors, tone, voice

Describe the situation without accusing the user. Avoid "you did X wrong" phrasing; focus
on the state and the fix. Neutral wording keeps a stressed user calm and oriented toward
recovery.

**Don't:**

```text
You entered an invalid email address.
```

**Do:**

```text
That email address doesn't look right. Check for typos and try again.
```

#### Always offer a realistic next step

- **Rule ID:** `errors-actionable-recovery`
- **Impact:** HIGH
- **Impact rationale:** An error with no way forward is a dead end
- **Tags:** errors, recovery, actions

Every error should point to something the user can actually do — retry, fix an input,
choose a different option, or contact support. Never give instructions the user can't
follow, and never block them without a path forward.

**Don't:**

```text
This file can't be uploaded.
```

**Do:**

```text
This file is too large to upload. Choose a file under 25 MB.
```

#### Place errors where the problem is

- **Rule ID:** `errors-place-at-source`
- **Impact:** HIGH
- **Impact rationale:** Users fix problems fastest where they're already looking
- **Tags:** errors, placement, forms

Put field-specific errors next to the field that has the issue, with a clear visual cue.
Put action failures inline near the trigger (for example, under the Save button the user
just clicked). Don't pile every error at the top of a long page with no field highlights.

**Don't:**

```text
[Top of page] There were 3 errors with your submission.
(fields below show no indication of which ones)
```

**Do:**

```text
Email
[ jane@ ]  ← Enter a valid email address.

[ Save ]
We couldn't save your changes. Try again.
```

#### Use modals only for must-resolve errors

- **Rule ID:** `errors-modal-only-when-blocking`
- **Impact:** MEDIUM
- **Impact rationale:** Full-screen modals for minor issues interrupt the user needlessly
- **Tags:** errors, placement, modals

Reserve modal (blocking) errors for problems the user must address before continuing, and
always include a primary action in the modal. For minor or recoverable issues, prefer
inline messages that don't interrupt the flow.

**Don't:**

```text
[Modal] Note saved as draft.   [OK]
```

**Do:**

```text
[Modal] Payment didn't go through
Your card was declined. Update your payment method to complete your purchase.
[ Update payment ]
```

### Empty & Loading States

#### Degrade gracefully — load and fail each section independently

- **Rule ID:** `states-graceful-degradation`
- **Impact:** CRITICAL
- **Impact rationale:** One slow or broken section shouldn't block or break the whole page
- **Tags:** states, loading, errors, resilience, graceful-degradation

A page looks like one screen, but its parts usually come from different sources that load at
different speeds and can fail on their own. Render each section as soon as its own data is
ready, and contain a section's failure to that section so the rest of the page stays usable.
Don't hold the whole page behind a single loading screen, and don't let one failed request
turn into a full-page error.

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

Think of it like ordering delivery from three restaurants: you eat what arrives instead of
throwing everything away because one order is late. Give each independently-loaded section
its own loading state and its own inline, retryable error scoped to that section — see
[`states-loading-match-scope`](#match-the-loading-indicator-to-the-scope-of-the-wait) for
choosing the indicator and
[`errors-place-at-source`](#place-errors-where-the-problem-is) for scoping the error.

#### Empty states explain purpose and offer a next step

- **Rule ID:** `states-empty-purpose-cta`
- **Impact:** HIGH
- **Impact rationale:** A blank screen leaves new users unsure what to do
- **Tags:** states, empty, onboarding, cta

Structure an empty state as `[What this area is for]. [Why it's empty]. [What to do next] +
clear button.` Make the primary action obvious rather than hiding it in a menu.

**Don't:**

```text
No projects.
```

**Do:**

```text
No projects yet. Create your first project to start tracking work.
[ Create project ]
```

#### Don't let empty states become dead ends

- **Rule ID:** `states-empty-no-dead-end`
- **Impact:** MEDIUM
- **Impact rationale:** Blank or blaming empty states feel broken and discouraging
- **Tags:** states, empty, tone

Never show only a title on a blank screen, and never blame the user for the emptiness.
Keep the tone encouraging and always surface a way forward. For "no results" states, help
the user adjust their query.

**Don't:**

```text
You haven't done anything yet.
```

**Do:**

```text
No results for "invoices 2025". Try a different keyword or adjust your filters.
```

#### Match the loading indicator to the scope of the wait

- **Rule ID:** `states-loading-match-scope`
- **Impact:** HIGH
- **Impact rationale:** The wrong indicator misrepresents how long and how much is loading
- **Tags:** states, loading, skeleton, progress

Pick the indicator that fits what's loading:

- **Skeleton screen** — a whole page or large content area; show layout first, then fill it.
- **Progress bar** — uploads, downloads, installs where duration is visible.
- **Inline spinner** — small, localized actions like Save or refreshing a list.
- **Optimistic UI** — low-stakes actions where instant feedback helps (likes, toggles).

**Don't:**

```text
[Full-page spinner with no layout, for 8 seconds]
```

**Do:**

```text
[Skeleton cards in the dashboard layout] Loading your dashboard…
```

#### Show that progress is happening, especially for long waits

- **Rule ID:** `states-loading-set-expectations`
- **Impact:** MEDIUM
- **Impact rationale:** Silent or static waits make users think the app is frozen
- **Tags:** states, loading, progress, expectations

For long or uncertain operations, communicate progress and, when possible, what remains.
Tell users if they can leave and how they'll be notified. Avoid a bare spinner for long
waits with no context.

**Don't:**

```text
Loading…
```

**Do:**

```text
Importing 120 contacts… 45% complete. You can leave this page; we'll email you when it's done.
```

#### Use optimistic UI only for low-stakes, reversible actions

- **Rule ID:** `states-optimistic-safe-only`
- **Impact:** MEDIUM
- **Impact rationale:** Optimistic updates on critical actions mislead users when they fail
- **Tags:** states, loading, optimistic, reliability

Update the UI immediately only when the action is easy to reverse (likes, toggles, reorder).
On failure, revert the change and show a short inline error. Don't use optimistic UI for
high-stakes, irreversible actions (large payments, deletions) without explicit confirmation.

**Don't:**

```text
[Charge $499 — instantly show "Payment complete" before the server responds]
```

**Do:**

```text
[Tap heart → fills immediately]
If the server fails: revert the heart, show "Couldn't save your like. Try again."
```

#### Show believable effort for complex work, never fake delays

- **Rule ID:** `states-labor-illusion-honest`
- **Impact:** LOW
- **Impact rationale:** Honest progress steps build trust; fake delays waste time and mislead
- **Tags:** states, loading, labor-illusion, trust

For genuinely complex operations (tax calculations, large searches, recommendations), show
brief, honest steps describing what the system is doing — this increases trust. Don't add
long artificial delays to simple actions, and don't claim work that isn't happening.

**Don't:**

```text
[Add a 5-second fake "Securing your data…" delay to a simple toggle]
```

**Do:**

```text
Comparing prices across airlines…
Reviewing your return for possible deductions…
```

Keep any deliberate wait short and purposeful, and never use it on time-critical flows.

### Forms & Input

#### Expose small choice sets instead of hiding them

- **Rule ID:** `forms-expose-small-choice-sets`
- **Impact:** HIGH
- **Impact rationale:** Hidden options increase interaction cost and make comparison harder.
- **Impact summary:** visible choices are faster to compare and select
- **Tags:** forms, dropdown, radio, chips
- **Source:** "Memorisely — ‘Here are 3 quick ways to make them easier to use’ (https://www.facebook.com/reel/1186154956819337), date unknown"

For roughly two to seven mutually exclusive options, prefer radio buttons or a segmented choice over a dropdown. For compact multi-select sets, use visible chips when practical and keep selections visible.

**Don't:** Hide three choices or a multi-select list behind a dropdown with an abstract label.

**Do:** Ask a clear question, show the available choices, and visibly preserve what is selected.

#### Validate inline as users leave each field

- **Rule ID:** `forms-inline-validation`
- **Impact:** HIGH
- **Impact rationale:** Batching all errors to submit forces users to rediscover every mistake
- **Tags:** forms, validation, feedback

Give feedback as soon as a field needs fixing — typically when the user leaves the field —
rather than letting them fill everything and showing all errors only after submit. Keep the
message directly under the field.

**Don't:**

```text
[User completes 9 fields, clicks Submit]
"Please fix the errors below" → 4 fields turn red at once
```

**Do:**

```text
Email
[ jane@example ]  ← Enter a valid email address.   (shown right after the user leaves the field)
```

#### Clearly mark required fields and what's missing

- **Rule ID:** `forms-mark-required`
- **Impact:** HIGH
- **Impact rationale:** Hidden requirements cause failed submits and frustration
- **Tags:** forms, required, clarity

Mark required fields visibly (for example "*" or "Required"). If submit is disabled until
the form is valid, also show what still needs attention — don't leave the user guessing why
the button won't work.

**Don't:**

```text
[ Submit ] (greyed out, no indication of what's incomplete)
```

**Do:**

```text
Full name *      [ Jane Doe ]
Work email *     [          ]  ← Required

[ Submit ] (enabled once required fields are valid)
```

#### Show limits and rules up front, updating live

- **Rule ID:** `forms-show-limits-and-rules`
- **Impact:** MEDIUM
- **Impact rationale:** Hidden constraints surface as errors only after the user fails
- **Tags:** forms, validation, limits, passwords

Show character limits, allowed formats, and password requirements before the user submits,
and update them as the user types. Check off password rules as they're met instead of
rejecting the password after the fact.

**Don't:**

```text
Password   [ ******** ]
(after submit) "Password does not meet requirements."
```

**Do:**

```text
Password   [ ******** ]
Use at least 8 characters, including a number and a capital letter.
✓ 8+ characters   ✓ a number   ✗ a capital letter

Bio   [ ... ]   120/160 characters
```

#### Pre-fill fields with data you already have

- **Rule ID:** `forms-prefill-known-data`
- **Impact:** MEDIUM
- **Impact rationale:** Re-typing known data adds friction and invites typos
- **Tags:** forms, prefill, friction

When the system already knows a value (name, email, saved address, current settings),
pre-fill it instead of asking the user to type it again. Keep pre-filled values editable.

**Don't:**

```text
[Checkout shows empty name, email, and address fields for a signed-in user]
```

**Do:**

```text
Shipping to: Jane Doe, 12 Main St — prefilled from your account. [ Edit ]
```

#### Accept flexible input formats and normalize in the backend

- **Rule ID:** `forms-forgiving-input`
- **Impact:** MEDIUM
- **Impact rationale:** Strict formatting rejects valid input the system could just interpret
- **Tags:** forms, input, formatting

Let users type phone numbers, dates, and similar values in natural formats, then normalize
them server-side. Don't force a rigid format when the system can reasonably interpret the
input.

**Don't:**

```text
Phone   [ 555-123-4567 ]  ← Format must be (555) 123-4567
```

**Do:**

```text
Phone   [ 5551234567 ]    (also accepts 555-123-4567 or (555) 123-4567)
Stored as +1-555-123-4567
```

### Success & Feedback

#### Confirm what succeeded, what's next, and a way forward

- **Rule ID:** `feedback-confirm-success`
- **Impact:** HIGH
- **Impact rationale:** Silent success leaves users unsure their action worked
- **Tags:** feedback, success, confirmation

Structure confirmations as `[What succeeded]. [What happens next / where to find it].
[Optional action].` Don't rely on a subtle change alone — state clearly that it worked.

**Don't:**

```text
[Form closes silently after submit]
```

**Do:**

```text
Your order is confirmed. We've emailed your receipt and tracking details.
[ View order ]
```

#### Use toasts only for low-importance, safe-to-miss updates

- **Rule ID:** `feedback-toasts-non-critical`
- **Impact:** MEDIUM
- **Impact rationale:** Critical info in a toast disappears before users can act on it
- **Tags:** feedback, toasts, non-blocking

Toasts are for brief, non-blocking status the user can safely miss. Don't put critical
errors or required actions in a toast, and don't stack multiple toasts that obscure content.

**Don't:**

```text
[Toast, auto-dismiss 3s] Payment failed — update your card to avoid losing access.
```

**Do:**

```text
[Toast] Saved as draft.
[Toast] You're back online. Syncing changes…
```

#### Use inline feedback when the user may need to act

- **Rule ID:** `feedback-inline-when-actionable`
- **Impact:** MEDIUM
- **Impact rationale:** Actionable status hidden in a transient toast gets missed
- **Tags:** feedback, inline, actions

When feedback relates to something the user might act on, place it inline near the related
element rather than in a disappearing toast. Keep it short.

**Don't:**

```text
[Toast, auto-dismiss] 2 of 5 rows failed to import.
```

**Do:**

```text
[Inline, under the table] 2 of 5 rows couldn't be imported. [ Review rows ]
Updated 2 seconds ago.
```

#### Keep key information somewhere persistent

- **Rule ID:** `feedback-persist-critical-info`
- **Impact:** MEDIUM
- **Impact rationale:** If a user looks away and misses a toast, they shouldn't lose anything important
- **Tags:** feedback, persistence, reliability

A toast or transient message must never be the only place important information lives. If
the user looks away and misses it, they should still find the status or result somewhere
persistent (a list, a detail page, an email, a banner).

**Don't:**

```text
[Only signal that an export finished is a 3-second toast]
```

**Do:**

```text
[Toast] Export ready.
+ The export also appears in Downloads with a permanent link, and we email it to you.
```

### Onboarding & Help

#### Focus onboarding on the few actions that lead to value

- **Rule ID:** `onboarding-focus-key-actions`
- **Impact:** HIGH
- **Impact rationale:** Long tours delay the first success and lose new users
- **Tags:** onboarding, activation, focus

Guide new users toward the small number of actions that produce a meaningful first result,
not a tour of every feature. Lead with one clear action.

**Don't:**

```text
[8-step product tour covering every menu before the user does anything]
```

**Do:**

```text
Create your first project to start organizing your work.
[ Create project ]
```

#### Offer short, context-specific help near complex controls

- **Rule ID:** `onboarding-just-in-time-help`
- **Impact:** MEDIUM
- **Impact rationale:** Help is most useful exactly where the question arises
- **Tags:** onboarding, help, tooltips

Put brief, just-in-time help next to the control it explains, rather than burying it in a
separate docs page. Don't explain obvious UI that users can infer.

**Don't:**

```text
[Tooltip on a Save button] Click this button to save your changes.
```

**Do:**

```text
[Help icon next to "Results per page"] This controls how many results appear per page.
```

#### Always let users skip or dismiss onboarding

- **Rule ID:** `onboarding-skippable`
- **Impact:** MEDIUM
- **Impact rationale:** Forced tours and walls of text frustrate users who want to start
- **Tags:** onboarding, control, friction

Let users skip, dismiss, or come back to onboarding later. Keep tips short and avoid walls
of text that block the user from getting started.

**Don't:**

```text
[Modal with 6 paragraphs and no close button until you scroll to the end]
```

**Do:**

```text
Quick tip: drag tasks to reorder them.   [ Got it ]   [ Skip tips ]
```
