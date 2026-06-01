---
title: Use inline feedback when the user may need to act
impact: MEDIUM
impactDescription: Actionable status hidden in a transient toast gets missed
tags: feedback, inline, actions
---

## Use inline feedback when the user may need to act

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
