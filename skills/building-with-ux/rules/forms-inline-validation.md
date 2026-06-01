---
title: Validate inline as users leave each field
impact: HIGH
impactDescription: Batching all errors to submit forces users to rediscover every mistake
tags: forms, validation, feedback
---

## Validate inline as users leave each field

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
