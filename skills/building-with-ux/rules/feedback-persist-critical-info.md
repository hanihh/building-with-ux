---
title: Keep key information somewhere persistent
impact: MEDIUM
impactDescription: If a user looks away and misses a toast, they shouldn't lose anything important
tags: feedback, persistence, reliability
---

## Keep key information somewhere persistent

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
