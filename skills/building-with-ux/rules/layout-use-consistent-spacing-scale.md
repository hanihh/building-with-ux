---
title: Use a consistent spacing scale
impact: HIGH
impactDescription: A shared rhythm prevents arbitrary gaps and makes components easier to adapt.
tags: spacing, rhythm, tokens
source: "Memorisely — ‘Save this before you freestyle your spacing again’ (https://www.facebook.com/reel/2009815326231629), date unknown"
---

## Use a consistent spacing scale

**Impact: HIGH (predictable rhythm improves hierarchy and maintainability)**

Choose a small base unit—commonly 4px—and derive gaps, padding, and control sizes from its multiples. Treat the scale as a system, then adjust for platform conventions, density, typography, and touch requirements.

**Don't:** Eyeball unrelated values such as 7px, 13px, and 19px throughout the same component family.

**Do:** Use named spacing tokens on a consistent scale and document justified exceptions.
