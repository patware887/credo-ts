---
'@credo-ts/openid4vc': patch
---

The OpenID4VC issuer and verifier endpoints now return a 400 `invalid_request` instead of a 500 `server_error` for malformed requests. This includes a request body that can't be parsed, an authorization response with no body or with a `response` that isn't a valid JWT, an encrypted response with an unsupported `alg` or `enc`, and an encrypted response whose content isn't a JSON object.

The JWE decrypt callback, which the holder also uses, now treats an unsupported `alg` or `enc` as a failed decryption instead of throwing an error.
