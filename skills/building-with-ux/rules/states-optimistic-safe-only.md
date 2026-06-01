---
title: Use optimistic UI only for low-stakes, reversible actions
impact: MEDIUM
impactDescription: Optimistic updates on critical actions mislead users when they fail
tags: states, loading, optimistic, reliability
---

## Use optimistic UI only for low-stakes, reversible actions

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
