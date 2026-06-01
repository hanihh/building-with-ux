---
title: Use plain language, not codes or stack traces
impact: HIGH
impactDescription: Technical dumps leave users stuck and erode trust
tags: errors, clarity, jargon
---

## Use plain language, not codes or stack traces

Describe the problem in everyday words. Don't expose raw error codes, stack traces, or
internal system names, and don't fall back to a vague "Something went wrong" with no
detail. If a support reference code is genuinely useful, keep it secondary to a plain
explanation.

**Don't:**

```text
Error 0x80070057: ERR_CONN_REFUSED at SyncService.flush()
```

**Do:**

```text
We couldn't sync your changes because we lost the connection. Check your internet and try again.
```
