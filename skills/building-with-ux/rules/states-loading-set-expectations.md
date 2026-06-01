---
title: Show that progress is happening, especially for long waits
impact: MEDIUM
impactDescription: Silent or static waits make users think the app is frozen
tags: states, loading, progress, expectations
---

## Show that progress is happening, especially for long waits

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
