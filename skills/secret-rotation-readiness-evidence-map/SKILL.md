---
name: secret-rotation-readiness-evidence-map
description: Review supplied, sanitized secret-lifecycle notes as a private readiness map of ownership, consumers, rotation, revocation, evidence, and gaps without handling credentials.
---

# Secret Rotation Readiness Evidence Map

Use when the user supplies a sanitized description of a secret lifecycle or rotation plan. Never request, receive, reveal, validate, or operate on an actual credential.

Use placeholders for every identifier. Record the secret class, owner, authorized consumers, storage boundary as described, issuance, distribution, renewal, overlap, revocation, failure handling, audit evidence, emergency path, dependencies, and unknowns.

Label each row `supplied observation`, `assumption`, `contradicted`, or `unknown`. Separate policy statements from evidence that a rotation path has worked. Return a private readiness map and proposed human-run checks marked `NOT RUN`.

Do not access vaults, files, repositories, clouds, accounts, networks, logs, or secret values; test credentials; rotate or revoke anything; change policy; create tickets; approve readiness; send; or publish. If sensitive material appears, stop and ask the user to redact it.

