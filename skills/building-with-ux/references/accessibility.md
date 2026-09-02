# Pillar 7 — Accessibility & Inclusion

**Default impact:** CRITICAL
**Rule prefixes:** `a11y-`

Usable by everyone — color contrast, keyboard navigation, screen-reader semantics and labels, reduced motion, dynamic type, and never relying on color alone.

## Agent checklist

- [ ] Test contrast in the real component context and never use color as the only signal.
- [ ] Provide generous touch targets, visible focus, logical keyboard order, and accessible names and semantics.
- [ ] Support reflow, dynamic type, zoom, reduced motion, and the product's required WCAG level.

## Instructions

### Test contrast in the real component context

- **Rule ID:** `a11y-test-contrast-in-context`
- **Impact:** CRITICAL
- **Impact rationale:** Brand intent does not compensate for unreadable content or controls.
- **Impact summary:** insufficient contrast excludes users
- **Tags:** accessibility, contrast, color, states
- **Source:** "Memorisely — ‘That brand colour looks great’ (https://www.facebook.com/reel/913195317925762), date unknown; W3C — WCAG 2.2 SC 1.4.3 and 1.4.11"

Check text, icons, borders, focus indicators, disabled states, and action labels against their actual surfaces in every supported theme. For web WCAG 2.2 AA, require at least 4.5:1 for normal text, 3:1 for large text, and 3:1 for meaningful non-text UI boundaries or states. If a brand color fails, adjust it for product use or introduce an accessible product color.

**Don't:** Force the exact brand swatch onto a primary button because it is canonical in marketing.

**Do:** Preserve the brand relationship while selecting a tested foreground/background pair that passes the applicable standard.

### Give touch controls generous target areas

- **Rule ID:** `a11y-size-touch-targets-generously`
- **Impact:** CRITICAL
- **Impact rationale:** Small or overlapping targets cause selection errors and exclude users with limited precision.
- **Impact summary:** controls must be operable without precise tapping
- **Tags:** accessibility, touch, mobile, navigation
- **Source:** "Memorisely — ‘Design better mobile tab bars’ (https://www.facebook.com/reel/2578041625882935), date unknown; W3C — WCAG 2.2 SC 2.5.8"

Size the hit area to the platform accessibility guidance, distribute neighboring targets consistently, and keep visible icons centered inside the larger target. For web WCAG 2.2 AA, targets must be at least 24×24 CSS px or have sufficient spacing under the criterion's exceptions; prefer 44×44 CSS px when space allows. Test at text scaling and on a real device.

**Don't:** Make only the 20px icon tappable or overlap a floating action with tab targets.

**Do:** Make the full tab cell interactive, pair icon and label, preserve spacing, and show a clear active state.
