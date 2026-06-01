---
title: Show limits and rules up front, updating live
impact: MEDIUM
impactDescription: Hidden constraints surface as errors only after the user fails
tags: forms, validation, limits, passwords
---

## Show limits and rules up front, updating live

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
