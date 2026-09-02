---
title: Layer primitive and semantic tokens
impact: HIGH
impactDescription: Raw values cannot explain purpose and make themes or global changes fragile.
tags: tokens, color, design-system, theming
source: "Memorisely — ‘When tokens have structure + purpose’ (https://www.facebook.com/reel/1812261746137188), date unknown"
---

## Layer primitive and semantic tokens

**Impact: HIGH (purposeful aliases keep usage consistent across themes and code)**

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
