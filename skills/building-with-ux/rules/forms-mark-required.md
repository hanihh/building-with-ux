---
title: Clearly mark required fields and what's missing
impact: HIGH
impactDescription: Hidden requirements cause failed submits and frustration
tags: forms, required, clarity
---

## Clearly mark required fields and what's missing

Mark required fields visibly (for example "*" or "Required"). If submit is disabled until
the form is valid, also show what still needs attention — don't leave the user guessing why
the button won't work.

**Don't:**

```text
[ Submit ] (greyed out, no indication of what's incomplete)
```

**Do:**

```text
Full name *      [ Jane Doe ]
Work email *     [          ]  ← Required

[ Submit ] (enabled once required fields are valid)
```
