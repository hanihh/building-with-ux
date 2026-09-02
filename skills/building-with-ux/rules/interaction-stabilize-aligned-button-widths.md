---
title: Stabilize button widths in aligned groups
impact: LOW
impactDescription: Large width jumps make repeated primary actions look uneven.
tags: buttons, alignment, localization
source: "Memorisely — ‘So many designers rely fully on Auto Layout’ (https://www.facebook.com/reel/905149311920923), date unknown"
---

## Stabilize button widths in aligned groups

**Impact: LOW (consistent geometry improves visual balance)**

When primary buttons repeat in an aligned group, use a shared minimum width or stretch them to the container while allowing long localized labels to grow or wrap safely.

**Don't:** Let short and long labels create visibly erratic widths in one comparison row.

**Do:** Apply the same minimum or container width, then test the longest supported label and text scaling.
