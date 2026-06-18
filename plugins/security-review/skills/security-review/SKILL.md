---
name: security-review
description: Use when writing or reviewing code that handles external input, authentication, secrets, database queries, file paths, or outbound requests — to check for common vulnerabilities before shipping. Triggers on security, auth, input, SQL, secret, token, upload, sanitize.
slash: true
---

# Security Review

Check code that touches untrusted input or sensitive operations against common vulnerabilities.

## Checklist

1. Validate and sanitize all external input (request bodies, params, headers, uploads) before using it.
2. Use parameterized queries / prepared statements — never build SQL or shell commands by string concatenation.
3. Enforce authorization on every protected action, not just authentication — confirm *this* user may do *this* thing.
4. Never log, echo, or commit secrets, tokens, or keys.
5. Avoid unsafe deserialization of untrusted data; prefer safe formats and allow-lists.
6. Guard against SSRF and path traversal when handling URLs or file paths — validate, normalize, and restrict targets.
7. Apply least privilege — credentials, tokens, and file permissions scoped to the minimum needed.

## Rules

- Assume all input is hostile until validated.
- Check authorization per action; never rely on client-side checks or hidden fields.
- When unsure whether something is exploitable, treat it as if it is and fix it.
