# Pillar 2 — Layout & Hierarchy

**Default impact:** HIGH
**Rule prefixes:** `layout-`

How space and structure guide the eye — grid, spacing rhythm, alignment, whitespace, focal point, content priority, and responsive behavior.

## Agent checklist

- [ ] Inventory supplied information, select what serves the task, and rank it before styling.
- [ ] Express primary, secondary, and tertiary emphasis through placement, scale, weight, contrast, alignment, and spacing.
- [ ] Group with proximity and whitespace first; add a surface, border, divider, or shadow only when it communicates a distinct job.
- [ ] Verify reading order, responsive flow, five-second comprehension, squint hierarchy, and information accuracy.

## Instructions

### Design the information hierarchy before styling

- **Rule ID:** `layout-group-and-rank-content`
- **Impact:** HIGH
- **Impact rationale:** A ranked content model creates an intentional reading order instead of decorating the source data order.
- **Impact summary:** people should understand content in the intended order
- **Tags:** hierarchy, grouping, proximity, information-architecture, composition
- **Source:** "Memorisely — ‘Visual hierarchy is what turns a pile of content into an actual interface’ (https://www.facebook.com/reel/4129723803984977), date unknown"

Do not blindly preserve the source data's order or give every item equal emphasis. Before
choosing a layout, inventory the available inputs, select the facts relevant to the user's
task, and rank them from the user's likely questions:

1. **Primary** — the outcome, object, or action the user came to understand or complete.
2. **Secondary** — facts needed to explain, compare, or act on the primary information.
3. **Tertiary** — supplementary context such as time, location, or provenance when it is not
   central to the current task.

These are importance levels, not fixed field categories or a fixed screen order. Identity,
location, or any other field may be primary when the user's task makes it central; context may
also appear first so the primary content is understandable. Cluster related items, choose an
intentional reading sequence, then express the ranking with placement, scale, weight,
contrast, and spacing. Within one decision region, prefer two or three clearly distinguishable
emphasis levels; if everything is prominent, nothing is.

Keep labels, values, status, and actions close to the content they describe. Space inside a
group must be visibly smaller than the space between groups. Use shared alignment and
repetition for facts users compare.

**Don't:** Make a generic activity title the largest element, spread related metrics and
metadata across the card, and style every value with the same weight because that is how the
API returned the fields.

**Do:** For an activity summary, group person and time as context; make the meaningful result
the focal point; align comparable metrics; place location with the map; accent a verified
achievement; and keep actions together after the content. Adapt this anatomy to the user's
task rather than treating it as a universal card template.

Before delivery, render the interface at its target size and check:

- **Five-second read:** Can someone identify what this is, the main result, and what they can do
  if an action is relevant?
- **Squint test:** When details blur, do the intended focal point and groups remain visible?
- **Truth:** Is every displayed fact accurate and traceable through any formatting,
  localization, conversion, or derivation? Did the design avoid inventing status, metrics,
  achievements, or backend behavior?

Research basis: [NN/g on visual hierarchy](https://www.nngroup.com/articles/visual-hierarchy-ux-definition/)
and [the proximity principle](https://www.nngroup.com/articles/gestalt-proximity/).

### Use one dominant alignment keyline

- **Rule ID:** `layout-use-one-alignment-keyline`
- **Impact:** MEDIUM
- **Impact rationale:** A stable scan anchor improves readability and makes relationships easier to see.
- **Impact summary:** fewer anchors make dense content easier to scan
- **Tags:** alignment, readability, keyline
- **Source:** "Memorisely — ‘Here’s something for your workflow’ (https://www.facebook.com/reel/1046094201648885), date unknown"

Prefer a shared left edge for multi-line or information-dense content. Mix alignment only when the change communicates a real relationship, such as a trailing value column.

**Don't:** Stack centered headings, descriptions, prices, and actions with different visual centers.

**Do:** Align the content to one keyline and use proximity to connect labels, values, and actions.

### Use whitespace before adding containers

- **Rule ID:** `layout-use-whitespace-before-containers`
- **Impact:** MEDIUM
- **Impact rationale:** Unnecessary boundaries add noise and make every group compete for attention.
- **Impact summary:** natural grouping keeps attention on content
- **Tags:** whitespace, cards, grouping, surfaces, borders, dividers
- **Source:** "Memorisely — ‘Craft is still everything’ (https://www.facebook.com/reel/989474367482162), date unknown"

Treat containment as a semantic signal, not a default layout technique. Every additional or
internal background, border, shadow, divider, or nested surface must communicate a distinct
relationship, state, elevation, interaction, readability need, or emphasis. A base canvas or
outer component surface may define the working region. If an inner boundary's job cannot be
named, remove it.

First attempt to form each group through proximity, alignment, typography, and whitespace.
Use a common surface when a boundary makes a genuinely separate region easier to understand,
or when it emphasizes an important region. Do not nest containers when the parent and child
boundaries communicate the same group. Do not use a divider where a deliberate spacing change
already makes the separation clear.

**Don't:** Put metrics in an outlined panel inside a profile card, add a divider below it, and
give the header another heavy block merely to make the layout feel structured.

**Do:** In a profile summary, keep the outer card as the component boundary, use one restrained
header surface if identity needs emphasis, let aligned metrics group through proximity, and
separate the action row with whitespace. Treat this as an example of the decision—not a fixed
profile-card template.

Before delivery, temporarily remove each inner boundary. If the layout becomes unclear, first
repair spacing, alignment, or typography. Restore the boundary only when it conveys meaning
that those lighter signals cannot communicate.

Research basis: [NN/g on common regions](https://www.nngroup.com/articles/common-region/)
and [visual hierarchy](https://www.nngroup.com/articles/visual-hierarchy-ux-definition/).

### Use a consistent spacing scale

- **Rule ID:** `layout-use-consistent-spacing-scale`
- **Impact:** HIGH
- **Impact rationale:** A shared rhythm prevents arbitrary gaps and makes components easier to adapt.
- **Impact summary:** predictable rhythm improves hierarchy and maintainability
- **Tags:** spacing, rhythm, tokens
- **Source:** "Memorisely — ‘Save this before you freestyle your spacing again’ (https://www.facebook.com/reel/2009815326231629), date unknown"

Choose a small base unit—commonly 4px—and derive gaps, padding, and control sizes from its multiples. Treat the scale as a system, then adjust for platform conventions, density, typography, and touch requirements.

**Don't:** Eyeball unrelated values such as 7px, 13px, and 19px throughout the same component family.

**Do:** Use named spacing tokens on a consistent scale and document justified exceptions.

### Design mobile screens as scrollable flows

- **Rule ID:** `layout-design-mobile-as-scrollable-flow`
- **Impact:** HIGH
- **Impact rationale:** Treating the viewport as a poster compresses content and misrepresents real use.
- **Impact summary:** the layout should match how the product is actually consumed
- **Tags:** mobile, responsive, scrolling
- **Source:** "Memorisely — ‘Quick mobile design tip’ (https://www.facebook.com/reel/2820140888323486), date unknown"

Use the viewport to test the initial experience, not as a fixed canvas that must contain everything. Extend the design vertically, prioritize the first view, and let lower-priority content follow in a deliberate scroll sequence.

**Don't:** Shrink type, controls, and spacing until the entire task fits inside one phone frame.

**Do:** Preserve readable content and touch targets, then design the complete scroll behavior and sticky regions.
