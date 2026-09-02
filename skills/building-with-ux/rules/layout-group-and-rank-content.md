---
title: Design the information hierarchy before styling
impact: HIGH
impactDescription: A ranked content model creates an intentional reading order instead of decorating the source data order.
tags: hierarchy, grouping, proximity, information-architecture, composition
source: "Memorisely — ‘Visual hierarchy is what turns a pile of content into an actual interface’ (https://www.facebook.com/reel/4129723803984977), date unknown"
---

## Design the information hierarchy before styling

**Impact: HIGH (people should understand content in the intended order)**

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
