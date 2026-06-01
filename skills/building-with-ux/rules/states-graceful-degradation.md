---
title: Degrade gracefully — load and fail each section independently
impact: CRITICAL
impactDescription: One slow or broken section shouldn't block or break the whole page
tags: states, loading, errors, resilience, graceful-degradation
---

## Degrade gracefully — load and fail each section independently

A page looks like one screen, but its parts usually come from different sources that load at
different speeds and can fail on their own. Render each section as soon as its own data is
ready, and contain a section's failure to that section so the rest of the page stays usable.
Don't hold the whole page behind a single loading screen, and don't let one failed request
turn into a full-page error.

**Don't:**

```text
[Whole page shows one spinner until profile, feed, and charts have all loaded]
[One failed request → the entire page is replaced by "Something went wrong"]
```

**Do:**

```text
[Stories render immediately; the feed shows a skeleton until it's ready]
[Sidebar is usable while the charts area shows its own loading state]
[If charts fail: that area shows "Couldn't load charts. Retry" — the rest of the page still works]
```

Think of it like ordering delivery from three restaurants: you eat what arrives instead of
throwing everything away because one order is late. Give each independently-loaded section
its own loading state and its own inline, retryable error scoped to that section — see
[states-loading-match-scope](states-loading-match-scope.md) for choosing the indicator and
[errors-place-at-source](errors-place-at-source.md) for scoping the error.
