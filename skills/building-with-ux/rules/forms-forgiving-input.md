---
title: Accept flexible input formats and normalize in the backend
impact: MEDIUM
impactDescription: Strict formatting rejects valid input the system could just interpret
tags: forms, input, formatting
---

## Accept flexible input formats and normalize in the backend

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
