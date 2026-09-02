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

Left-align and prioritize navigation, group related items, keep the primary visible set concise (the source recommends no more than five top-level items; move settings, support, and account into a grouped utility block), and integrate utilities coherently. Let search fill the sidebar width and show its keyboard shortcut; render notification badges in the alert feedback color, right-aligned, and check their contrast. Provide hover, focus, and active states. Every collapsed item still needs a programmatic accessible name; a tooltip may supplement pointer/keyboard discovery but never substitutes for that name or for a usable touch pattern. Prefer an expandable drawer when icon-only navigation would be ambiguous on touch.

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

### Keep tab bars flat, labeled, and legible over content

- **Rule ID:** `nav-keep-tab-bar-flat-and-labeled`
- **Impact:** HIGH
- **Impact rationale:** A tab bar is the user's map; decorative shapes and missing labels remove orientation on every screen.
- **Impact summary:** the bottom bar must read as one predictable row of destinations
- **Tags:** tab-bar, mobile, navigation, wayfinding, labels
- **Source:** "Memorisely — ‘Design better mobile tab bars’ (https://www.facebook.com/reel/2578041625882935), date unknown"

Place every destination inside the bar as an icon with a text label; do not float a raised action button over the bar or break the row for one item. Use one icon family, give the active tab a clear filled or colored state, keep spacing equal across tabs, and show notification counts with a small badge on the relevant tab. Let the bar sit over scrolling content with a translucent or blurred background so users see that more content continues beneath it. For sizing, follow `a11y-size-touch-targets-generously`.

**Don't:** An oversized create button overlapping the center of the bar, uppercase labels, and an active tab that only changes hue slightly.

**Do:** Five or fewer evenly spaced tabs, each with icon and label, a distinct active state, a profile tab that can carry the avatar and a badge, and a bar that remains legible over photos and dark content.
