# Pillar 3 — Visual Design

**Default impact:** HIGH
**Rule prefixes:** `visual-`

The surface treatment — color systems and contrast, type scale and pairing, elevation and shadow, iconography, and style consistency.

## Agent checklist

- [ ] Give every color a semantic job and test contrast in the rendered component context.
- [ ] For reusable or themed UI, use raw value → primitive → semantic role → component; components consume semantic roles.
- [ ] Use one coherent type, radius, elevation, and icon system; test typography at its actual use size.

## Instructions

### Match nested radii to their padding

- **Rule ID:** `visual-match-nested-radii-to-padding`
- **Impact:** MEDIUM
- **Impact rationale:** Equal inner and outer radii create visibly uneven corner gaps.
- **Impact summary:** concentric corners look intentional
- **Tags:** radius, geometry, padding
- **Source:** "Memorisely — ‘This is a gooooood tip’ (https://www.facebook.com/reel/2350497468756858), date unknown"

For uniformly padded nested rounded shapes, start with `outer radius = inner radius + padding`. Verify optically when padding differs by axis or shapes are not concentric.

**Don't:** Apply the same radius to a card and its inset image.

**Do:** Increase the outer radius by the inset so the visible gap follows the curve evenly.

### Give every color a job

- **Rule ID:** `visual-give-color-a-job`
- **Impact:** HIGH
- **Impact rationale:** Competing decorative colors weaken hierarchy and semantic meaning.
- **Impact summary:** limited semantics make important color easier to notice
- **Tags:** color, hierarchy, semantics
- **Source:** "Memorisely — ‘Too many colours can turn a UI into a bit of a circus’ (https://www.facebook.com/reel/1155559809871435), date unknown"

Begin with neutral backgrounds and surfaces. Add color for action, feedback, state, identity, or data meaning, and remove it when it serves none of those purposes.

**Don't:** Color avatars, icons, navigation, cards, and headings independently for decoration.

**Do:** Use a neutral base, an accessible primary accent, and a small semantic feedback palette.

### Build dark-mode depth with dark surfaces

- **Rule ID:** `visual-build-dark-mode-depth-with-surfaces`
- **Impact:** HIGH
- **Impact rationale:** Light cards and bright borders break dark-mode hierarchy and create glare.
- **Impact summary:** tonal elevation preserves hierarchy without glare
- **Tags:** dark-mode, elevation, surfaces, color
- **Source:** "Memorisely — ‘Tip’s to Design better Dark Mode UI’ (https://www.facebook.com/reel/773670201159857), date unknown"

Use the darkest tone for the recessed screen background and progressively lighter dark tones for elevated surfaces. Subdue borders and saturated accents; pure black is optional, not required.

**Don't:** Paste a white or light-mode card onto a dark background or outline every surface in white.

**Do:** Express elevation through restrained tonal steps and recheck text, icons, borders, and states in context.

### Test typefaces at their real use sizes

- **Rule ID:** `visual-test-typefaces-at-use-size`
- **Impact:** HIGH
- **Impact rationale:** Display samples hide legibility problems that appear in dense or small interface text.
- **Impact summary:** UI typography must survive realistic content and density
- **Tags:** typography, readability, legibility
- **Source:** "Memorisely — ‘This will help you make smarter font choices’ (https://www.facebook.com/reel/2343808059445484), date unknown"

Evaluate open counters, x-height, ascenders, descenders, baseline, line height, numerals, kerning, and available weights using actual interface strings at target sizes.

**Don't:** Choose a font from one large alphabet sample in a picker.

**Do:** Run micro-tests for labels, paragraphs, tables, numbers, long names, and multiple scripts before committing.

### Use one coherent icon family

- **Rule ID:** `visual-use-one-icon-family`
- **Impact:** MEDIUM
- **Impact rationale:** Mixed stroke, fill, size, and geometry make controls harder to recognize consistently.
- **Impact summary:** consistent visual grammar improves recognition
- **Tags:** icons, consistency, design-system
- **Source:** "Memorisely — ‘Friendly reminder that you don’t need to design your own icons’ (https://www.facebook.com/reel/1349852363307091), date unknown"

Prefer an established, accessible library that covers the product's needs and maps cleanly to implementation. Define size, stroke, fill, alignment, and active-state rules before adding exceptions.

**Don't:** Mix custom icons with unrelated solid, outline, duotone, and 3D sets in the same navigation.

**Do:** Use one family for functional controls and reserve other styles for clearly separate illustrative roles.

### Layer primitive and semantic tokens

- **Rule ID:** `visual-layer-primitive-and-semantic-tokens`
- **Impact:** HIGH
- **Impact rationale:** Raw values cannot explain purpose and make themes or global changes fragile.
- **Impact summary:** purposeful aliases keep usage consistent across themes and code
- **Tags:** tokens, color, design-system, theming
- **Source:** "Memorisely — ‘When tokens have structure + purpose’ (https://www.facebook.com/reel/1812261746137188), date unknown"

For reusable or themed product UI, build color in three layers: raw values such as `#ffffff`, ordered primitives such as
`gray/100`, and semantic aliases such as `color/background/fill` or
`color/text/secondary`. Raw values define primitives; semantic aliases reference primitives;
components consume semantic aliases.

Name semantic tokens by purpose and state—background, surface, text, border, action, success,
warning, error, disabled—not by the color they currently contain. Map light, dark, and
high-contrast themes by changing the semantic mapping instead of editing component styles.
Document the primitive scale direction because names such as `gray/100` do not have a universal
meaning. A token diagram proves the architecture, not the palette: use supplied brand or product
colors, or state assumptions, rather than inventing a full theme from one example swatch.

**Don't:** Apply hex values or primitive tokens such as `gray/100` directly throughout
components, or name a component token after its current appearance such as `lightGrayCard`.

**Do:** Map `raw value → primitive → semantic role`, then consume only the semantic role in
component design and code. Raw values belong in token definitions; exceptional data
visualization palettes should still expose semantic series roles.

```css
:root {
  --gray-100: #ffffff;
  --gray-900: #161616;
  --color-background-fill: var(--gray-100);
  --color-text-primary: var(--gray-900);
}

.card {
  background: var(--color-background-fill);
  color: var(--color-text-primary);
}

[data-theme="dark"] {
  --color-background-fill: var(--gray-900);
  --color-text-primary: var(--gray-100);
}
```

Before delivery, inspect component styles for raw color literals and direct primitive usage.
Move each occurrence into the token layers unless a documented technical constraint requires
an exception, such as `transparent`, `currentColor`, user/data-driven colors, or immutable
brand assets. Test every documented foreground/background and interaction-state combination
for contrast in each supported theme. For a disposable prototype, local semantic variables may
replace a full primitive scale, but do not scatter unexplained literals through component code.
