---
title: Use whitespace before adding containers
impact: MEDIUM
impactDescription: Unnecessary boundaries add noise and make every group compete for attention.
tags: whitespace, cards, grouping, surfaces, borders, dividers
source: "Memorisely — ‘Craft is still everything’ (https://www.facebook.com/reel/989474367482162), date unknown"
---

## Use whitespace before adding containers

**Impact: MEDIUM (natural grouping keeps attention on content)**

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
