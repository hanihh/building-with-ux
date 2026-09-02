---
title: Preserve hierarchy when sidebars collapse
impact: HIGH
impactDescription: Collapsing labels must not remove orientation or interaction feedback.
tags: sidebar, navigation, wayfinding
source: "Memorisely — ‘10 Supafast updates to help you design a better sidebar navigation’ (https://www.facebook.com/reel/3646814668927376), date unknown"
---

## Preserve hierarchy when sidebars collapse

**Impact: HIGH (users need stable wayfinding in both states)**

Left-align and prioritize navigation, group related items, keep the primary visible set concise, and integrate utilities coherently. Provide hover, focus, and active states. Every collapsed item still needs a programmatic accessible name; a tooltip may supplement pointer/keyboard discovery but never substitutes for that name or for a usable touch pattern. Prefer an expandable drawer when icon-only navigation would be ambiguous on touch.

**Don't:** Hide text and leave an undifferentiated column of icons with no active state.

**Do:** Keep order and grouping stable, expose accessible names, make search and utilities discoverable, and verify expanded, collapsed, keyboard, touch, screen-reader, and dark-mode states.
