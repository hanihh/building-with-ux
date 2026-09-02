# Pillar 5 — Navigation & Information Architecture

**Default impact:** HIGH
**Rule prefixes:** `nav-`

How people move and orient — information architecture, wayfinding, menus, search, back behavior, and deep linking.

## Agent checklist

- [ ] Make current location, available destinations, and the way back predictable.
- [ ] Preserve hierarchy as navigation changes form across viewport sizes.
- [ ] Use visual anchors when they make repeated choices faster to recognize.

## Instructions

### Preserve hierarchy when sidebars collapse

- **Rule ID:** `nav-structure-collapsible-sidebars`
- **Impact:** HIGH
- **Impact rationale:** Collapsing labels must not remove orientation or interaction feedback.
- **Impact summary:** users need stable wayfinding in both states
- **Tags:** sidebar, navigation, wayfinding
- **Source:** "Memorisely — ‘10 Supafast updates to help you design a better sidebar navigation’ (https://www.facebook.com/reel/3646814668927376), date unknown"

Left-align and prioritize navigation, group related items, keep the primary visible set concise, and integrate utilities coherently. Provide hover, focus, and active states. Every collapsed item still needs a programmatic accessible name; a tooltip may supplement pointer/keyboard discovery but never substitutes for that name or for a usable touch pattern. Prefer an expandable drawer when icon-only navigation would be ambiguous on touch.

**Don't:** Hide text and leave an undifferentiated column of icons with no active state.

**Do:** Keep order and grouping stable, expose accessible names, make search and utilities discoverable, and verify expanded, collapsed, keyboard, touch, screen-reader, and dark-mode states.

### Use visual anchors for fast repeated choices

- **Rule ID:** `nav-use-visual-anchors-for-fast-choices`
- **Impact:** MEDIUM
- **Impact rationale:** Recognizable shapes reduce repeated text scanning when options must be compared quickly.
- **Impact summary:** recognition can shorten comparison time
- **Tags:** navigation, icons, recognition, scanning
- **Source:** "Memorisely — ‘Uber uses visual anchoring across their app’ (https://www.facebook.com/reel/3183536318702578), date unknown"

Pair repeated options with distinct, consistent, meaningful icons, silhouettes, or thumbnails. Keep text labels for clarity and accessibility; the visual anchor supports recognition rather than replacing meaning.

**Don't:** Present a long list of visually identical text blocks for choices with recognizable categories.

**Do:** Pair each option with a stable shape and label so users can scan, recognize, then confirm.
