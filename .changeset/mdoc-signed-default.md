---
'@credo-ts/core': patch
---

`Mdoc.sign` no longer fails when `validFrom` is set to `new Date()` and `signed` is not set. If `validFrom` is at most `validitySkewSeconds` in the past, `signed` now defaults to `validFrom` instead of the current time.
