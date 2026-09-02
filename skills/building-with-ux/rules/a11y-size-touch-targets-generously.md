---
title: Give touch controls generous target areas
impact: CRITICAL
impactDescription: Small or overlapping targets cause selection errors and exclude users with limited precision.
tags: accessibility, touch, mobile, navigation
source: "Memorisely — ‘Design better mobile tab bars’ (https://www.facebook.com/reel/2578041625882935), date unknown; W3C — WCAG 2.2 SC 2.5.8"
---

## Give touch controls generous target areas

**Impact: CRITICAL (controls must be operable without precise tapping)**

Size the hit area to the platform accessibility guidance, distribute neighboring targets consistently, and keep visible icons centered inside the larger target. For web WCAG 2.2 AA, targets must be at least 24×24 CSS px or have sufficient spacing under the criterion's exceptions; prefer 44×44 CSS px when space allows. Test at text scaling and on a real device.

**Don't:** Make only the 20px icon tappable or overlap a floating action with tab targets.

**Do:** Make the full tab cell interactive, pair icon and label, preserve spacing, and show a clear active state.
