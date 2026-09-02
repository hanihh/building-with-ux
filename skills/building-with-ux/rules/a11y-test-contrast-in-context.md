---
title: Test contrast in the real component context
impact: CRITICAL
impactDescription: Brand intent does not compensate for unreadable content or controls.
tags: accessibility, contrast, color, states
source: "Memorisely — ‘That brand colour looks great’ (https://www.facebook.com/reel/913195317925762), date unknown; W3C — WCAG 2.2 SC 1.4.3 and 1.4.11"
---

## Test contrast in the real component context

**Impact: CRITICAL (insufficient contrast excludes users)**

Check text, icons, borders, focus indicators, disabled states, and action labels against their actual surfaces in every supported theme. For web WCAG 2.2 AA, require at least 4.5:1 for normal text, 3:1 for large text, and 3:1 for meaningful non-text UI boundaries or states. If a brand color fails, adjust it for product use or introduce an accessible product color.

**Don't:** Force the exact brand swatch onto a primary button because it is canonical in marketing.

**Do:** Preserve the brand relationship while selecting a tested foreground/background pair that passes the applicable standard.
