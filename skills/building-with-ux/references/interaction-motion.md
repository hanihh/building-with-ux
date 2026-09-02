# Pillar 4 — Interaction & Motion

**Default impact:** HIGH
**Rule prefixes:** `interaction-`

How the interface responds — interaction states, affordances, animation timing and easing, gestures, touch targets, and microinteractions.

## Agent checklist

- [ ] Specify hover, pressed, focus, disabled, loading, success, and failure states where applicable.
- [ ] Choose transitions by the relationship between views and animate according to visual hierarchy.
- [ ] Keep aligned controls stable and state the consequence of destructive actions before confirmation.

## Instructions

### Choose transitions by the information relationship

- **Rule ID:** `interaction-choose-transition-by-relationship`
- **Impact:** MEDIUM
- **Impact rationale:** Matching motion to the change preserves orientation.
- **Impact summary:** motion should explain what changed
- **Tags:** motion, transitions, navigation
- **Source:** "Memorisely — ‘3 UI transitions every designer should know’ (https://www.facebook.com/reel/1791233011835685), date unknown"

Use a context transition when content changes inside stable structure, a drill transition between hierarchy levels, and continuity when a shared element persists into the next state.

**Don't:** Apply the same dissolve to tabs, list-to-detail navigation, and card expansion.

**Do:** Keep tabs structurally stable, move list-to-detail as a hierarchy change, and morph a shared card into its detail view.

### Animate according to visual hierarchy

- **Rule ID:** `interaction-animate-by-hierarchy`
- **Impact:** MEDIUM
- **Impact rationale:** Equal motion everywhere competes for attention and obscures the main change.
- **Impact summary:** the dominant motion should match the dominant change
- **Tags:** motion, hierarchy, overlays
- **Source:** "Memorisely — ‘Motion isn’t just for vibes’ (https://www.facebook.com/reel/668612516190284), date unknown"

Keep persistent controls stable or fade them subtly. Give the primary changing content the clearest movement, let overlays enter from a plausible origin, and stagger secondary elements only when it clarifies sequence.

**Don't:** Move every control, label, and background with equal intensity.

**Do:** Animate the changed card or sheet, preserve orientation, keep duration task-focused, and provide a reduced-motion equivalent.

### State consequences in destructive confirmations

- **Rule ID:** `interaction-confirm-destructive-actions-with-consequences`
- **Impact:** CRITICAL
- **Impact rationale:** Generic questions fail to help users distinguish a safe action from irreversible loss.
- **Impact summary:** users must understand irreversible outcomes
- **Tags:** destructive, confirmation, modal, microcopy
- **Source:** "Memorisely — ‘Are you sure?’ is one of the most common confirmation modals’ (https://www.facebook.com/reel/981228391628411), date unknown"

Inform rather than ask. Use a verb-plus-object title, state the consequence and reversibility, label the destructive action directly, and provide **Cancel** plus an obvious close path.

**Don't:** “Are you sure?” with buttons **Yes** and **No**.

**Do:** “Delete folder” — “This permanently deletes 18 files.” Actions: **Delete** and **Cancel**.

### Stabilize button widths in aligned groups

- **Rule ID:** `interaction-stabilize-aligned-button-widths`
- **Impact:** LOW
- **Impact rationale:** Large width jumps make repeated primary actions look uneven.
- **Impact summary:** consistent geometry improves visual balance
- **Tags:** buttons, alignment, localization
- **Source:** "Memorisely — ‘So many designers rely fully on Auto Layout’ (https://www.facebook.com/reel/905149311920923), date unknown"

When primary buttons repeat in an aligned group, use a shared minimum width or stretch them to the container while allowing long localized labels to grow or wrap safely.

**Don't:** Let short and long labels create visibly erratic widths in one comparison row.

**Do:** Apply the same minimum or container width, then test the longest supported label and text scaling.
