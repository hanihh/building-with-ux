---
title: Match nested radii to their padding
impact: MEDIUM
impactDescription: Equal inner and outer radii create visibly uneven corner gaps.
tags: radius, geometry, padding
source: "Memorisely — ‘This is a gooooood tip’ (https://www.facebook.com/reel/2350497468756858), date unknown"
---

## Match nested radii to their padding

**Impact: MEDIUM (concentric corners look intentional)**

For uniformly padded nested rounded shapes, start with `outer radius = inner radius + padding`. Verify optically when padding differs by axis or shapes are not concentric.

**Don't:** Apply the same radius to a card and its inset image.

**Do:** Increase the outer radius by the inset so the visible gap follows the curve evenly.
