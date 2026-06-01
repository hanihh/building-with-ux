---
title: Match the loading indicator to the scope of the wait
impact: HIGH
impactDescription: The wrong indicator misrepresents how long and how much is loading
tags: states, loading, skeleton, progress
---

## Match the loading indicator to the scope of the wait

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
