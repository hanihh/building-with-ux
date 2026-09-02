# Pillar 3 — Visual Design

**Default impact:** HIGH
**Rule prefixes:** `visual-`

The surface treatment — color systems and contrast, type scale and pairing, elevation and shadow, iconography, and style consistency.

## Agent checklist

- [ ] Give every color a semantic job and test contrast in the rendered component context.
- [ ] For reusable or themed UI, use raw value → primitive → semantic role → component; components consume semantic roles.
- [ ] Use one coherent type, radius, elevation, and icon system; test typography at its actual use size.
- [ ] Name semantic tokens as `color-element-priority-state` and give components the same variant/tone/size/state vocabulary in design and code.

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

Keep the feedback palette exclusive: red, amber, and green must only appear when they signal error, warning, or success. A red brand accent or red decorative background on a form makes the whole screen read as a failure state; pick a neutral or a non-feedback brand hue instead. (Source: Memorisely — ‘Sign-up forms that actually work? Yes please.’ https://www.facebook.com/reel/775152848372082)

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

To subdue saturated accents that glow on dark surfaces, a practical starting heuristic is the 70/60 rule: render warm accent colors (reds, oranges, yellows) at roughly 70% opacity and cool accent colors (blues, greens, purples) at roughly 60% over the dark surface, then recheck contrast. Dark mode does not have to be gray: deep purples, greens, or blues work as the surface family as long as the same recessed-to-elevated tonal steps apply. (Sources: Memorisely — ‘Dark mode tip: lower warm colours to 70% opacity and cool colours to 60%’ https://www.facebook.com/reel/889874220424478; the dark-mode reel cited above.)

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

### Name semantic tokens by element, priority, and state

- **Rule ID:** `visual-name-semantic-tokens-by-element-priority-state`
- **Impact:** HIGH
- **Impact rationale:** Without a shared grammar, semantic tokens drift into ad-hoc names that neither designers, engineers, nor coding agents can predict.
- **Impact summary:** a predictable token name tells a reader where the color is used before they look it up
- **Tags:** tokens, naming, color, design-system, theming
- **Source:** "Memorisely — ‘Stoooooppp this one for a better design system’ (https://www.facebook.com/reel/1243799291240978), date unknown; Memorisely — ‘Your token naming is either doing the work or creating it’ (https://www.facebook.com/reel/1399145152109265), date unknown; Memorisely — ‘Tokens get messy fast if the structure isn’t clear’ (https://www.facebook.com/reel/2353008908475038), date unknown"

Build every semantic color token from the same ordered blocks: `color` → UI element → priority → state. Use a fixed element vocabulary that mirrors how the UI is layered: `background` (the screen), `surface` (layout regions on the background), `fill` (component backgrounds), `border`, `text`, and `icon`. Add a priority block when the element has ranked variants (`primary`, `secondary`, `tertiary`, `brand`, `success`, `warning`, `error`) and a state block only for interactive tokens (`hover`, `pressed`, `disabled`, `selected`). Omit a block instead of inventing filler.

**Don't:** `blueButton`, `cardBg2`, `textDarkGray`, `color/accent-hover-alt`.

**Do:** `color-background`, `color-surface-elevated`, `color-fill-primary-hover`, `color-border-error`, `color-text-secondary`, `color-icon-disabled`. Apply the same grammar in Figma variable groups (`color/fill/primary/hover`) and in code (`--color-fill-primary-hover`) so one name works in both. This rule names the semantic layer described in `visual-layer-primitive-and-semantic-tokens`; primitives keep their own `family-step` names such as `gray-100`.

### Align component names and props with code

- **Rule ID:** `visual-align-component-names-and-props-to-code`
- **Impact:** HIGH
- **Impact rationale:** When design variants and code props use different words, every handoff becomes translation and the two sources drift apart.
- **Impact summary:** one vocabulary for design and implementation removes a whole class of inconsistencies
- **Tags:** components, naming, props, design-system, react, figma
- **Source:** "Memorisely — ‘A simple way to structure components so they’re consistent, scalable, and easy to work with’ (https://www.facebook.com/reel/33199561629689036), date unknown; Memorisely — ‘Figma properties should align to React props’ (https://www.facebook.com/reel/992791810300297), date unknown"

Name a component with its full literal noun (`button`, `text-field`, `switch`), never an abbreviation such as `btn`. Describe variants with the same ordered modifiers in design and code: **purpose or emphasis** (`variant`: primary, secondary, tertiary, ghost), **intent or tone** (`tone`: neutral, critical, success), **size** (`size`: sm, md, lg), and, for interactive components, **state** (`state`: default, hover, pressed, disabled, loading). A designer switching a button from primary to secondary should change one modifier; an engineer should change one prop with the same name and value.

**Don't:** Figma variants named `Btn / Blue / Big / Hovered` while the code exposes `type="cta" color="brand" large`.

**Do:** Figma `button` with properties `variant=secondary`, `tone=critical`, `size=md`, `state=hover`, and a component signature such as `<Button variant="secondary" tone="critical" size="md">`. Before delivery, list every design property and confirm a prop with the same name and value set exists in the implementation, and the reverse.

### Build gradients with a fixed hue and four steps

- **Rule ID:** `visual-build-gradients-with-fixed-hue-and-four-steps`
- **Impact:** MEDIUM
- **Impact rationale:** Two-stop gradients that jump between a light tint and a dark shade pass through a gray, muddy middle that reads as low quality.
- **Impact summary:** a gradient should look like light falling on one color
- **Tags:** gradient, color, hsl, surfaces
- **Source:** "Memorisely — ‘Most gradients look muddy’ (https://www.facebook.com/reel/1463647358693378), date unknown"

Define gradients in HSL and keep the hue constant across all stops; vary saturation and lightness only. Use four stops that model a light source: **light source** (highest saturation and lightness), **hold** (the main body tone), **falloff** (darker transition), **anchor** (the darkest stop). Change the angle to move the light; change only the hue value to create a matching gradient in another color.

**Don't:** Interpolate from a random pale hex to a random dark hex and accept the gray band in between.

**Do:** `hsl(220 90% 70%) → hsl(220 80% 55%) → hsl(220 75% 40%) → hsl(220 70% 25%)` at one angle, reused as a family by shifting only the hue. Test text contrast against the hold and falloff stops, not only against the ends.

### Use a type scale with paired line heights

- **Rule ID:** `visual-use-type-scale-with-paired-line-heights`
- **Impact:** MEDIUM
- **Impact rationale:** Guessed sizes and unpaired line heights produce uneven vertical rhythm and inconsistent spacing between text blocks.
- **Impact summary:** every text role should have a fixed size and line height on the spacing grid
- **Tags:** typography, type-scale, line-height, landing-page, tokens
- **Source:** "Memorisely — ‘Here’s our guidelines to help you get started’ (https://www.facebook.com/reel/1363993034306992), date unknown; Memorisely — ‘Stop guessing your website spacing’ (https://www.facebook.com/reel/1407832057169874), date unknown"

Define each text role once as a size/line-height pair whose line height is a multiple of the spacing base unit, then reuse it everywhere. A marketing-page starting point at small, medium, and large breakpoints:

| Role | Small | Medium | Large |
|---|---|---|---|
| Hero heading | 64 / 72 | 72 / 80 | 80 / 96 |
| Hero body | 16 / 24 | 20 / 28 | 24 / 32 |
| Button label | 14 / 20 | 16 / 24 | 18 / 28 |
| Label / caption | 12 / 16 | 12 / 16 | 14 / 16 |
| Gap between hero text blocks | 24 | 32 | 40 |

The source suggests 10px for the smallest label; this skill floors labels at 12px so they remain legible and pass `a11y-test-contrast-in-context` under zoom and dynamic type. Product UI usually needs a smaller top of the scale than the hero values above; keep the pairing discipline and adjust the numbers.

**Don't:** Set a heading to 61px with line height "auto" and a caption to 11px, then eyeball the gap between them.

**Do:** Expose the roles as tokens (`--text-hero-lg: 80px/96px`) and step the whole scale by breakpoint rather than resizing individual elements.

### Avoid all-caps text in labels and controls

- **Rule ID:** `visual-avoid-all-caps-ui-text`
- **Impact:** MEDIUM
- **Impact rationale:** Uppercase strings lose word shape, read slower, and feel like shouting in buttons, tabs, and dialog titles.
- **Impact summary:** sentence or title case keeps labels fast to read and calm in tone
- **Tags:** typography, labels, buttons, tabs, readability
- **Source:** "Memorisely — ‘“Are you sure?” is one of the most common confirmation modals’ (https://www.facebook.com/reel/981228391628411), date unknown; Memorisely — ‘Design better mobile tab bars’ (https://www.facebook.com/reel/2578041625882935), date unknown"

Write button labels, tab labels, dialog titles, and navigation items in sentence case or title case according to the platform convention. Reserve uppercase for established abbreviations and very short overline labels with added letter spacing, never for the primary action or a warning.

**Don't:** `DELETE ACCOUNT`, `HOME · SEARCH · PROFILE`, `ARE YOU SURE?`

**Do:** `Delete account`, `Home · Search · Profile`, `Delete folder` as the dialog title. Do not use `text-transform: uppercase` as a hierarchy tool; use weight, size, and color instead.
