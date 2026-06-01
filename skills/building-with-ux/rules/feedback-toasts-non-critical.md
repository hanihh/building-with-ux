---
title: Use toasts only for low-importance, safe-to-miss updates
impact: MEDIUM
impactDescription: Critical info in a toast disappears before users can act on it
tags: feedback, toasts, non-blocking
---

## Use toasts only for low-importance, safe-to-miss updates

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
