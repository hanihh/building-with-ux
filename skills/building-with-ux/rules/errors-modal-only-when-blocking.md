---
title: Use modals only for must-resolve errors
impact: MEDIUM
impactDescription: Full-screen modals for minor issues interrupt the user needlessly
tags: errors, placement, modals
---

## Use modals only for must-resolve errors

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
