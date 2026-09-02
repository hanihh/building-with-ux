---
title: Layer primitive and semantic tokens
impact: HIGH
impactDescription: Raw values cannot explain purpose and make themes or global changes fragile.
tags: tokens, color, design-system, theming
source: "Memorisely — ‘When tokens have structure + purpose’ (https://www.facebook.com/reel/1812261746137188), date unknown"
---

## Layer primitive and semantic tokens

**Impact: HIGH (purposeful aliases keep usage consistent across themes and code)**

Separate raw values, ordered primitives such as `gray/100`, and semantic aliases such as `color/text/secondary`. Name semantic tokens by element, purpose or priority, and state; map light and dark modes through aliases.

**Don't:** Apply hex values or vaguely named tokens such as `gray2` directly throughout components.

**Do:** Map `raw value → primitive → semantic role`, then consume the semantic role in design and code.
