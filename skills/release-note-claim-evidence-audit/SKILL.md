---
name: release-note-claim-evidence-audit
description: Audit a supplied release-note draft against sanitized change evidence and return private claim-safe corrections without publishing or rewriting the release.
---

# Release Note Claim Evidence Audit

Use when a release-note draft already exists and the user wants its claims checked against supplied evidence. This is an audit, not a release-note writing or publishing workflow.

Use only the draft and sanitized tickets, change summaries, test results, limitations, and rollout facts supplied in the conversation or explicitly selected as read-only.

For each claim, record the audience, stated behavior, evidence source, scope, version, availability, limitation, and confidence. Label it `supported`, `contradicted`, or `insufficient`. Flag invented benefits, omitted limitations, future work stated as shipped, partial rollout stated as universal, and verification claims that are not current.

Return a private claim ledger, gaps, and proposed claim-safe replacement sentences. Mark replacements `PROPOSED — NOT PUBLISHED`.

Do not access tickets, repositories, builds, files, networks, accounts, or analytics; run checks; change the draft file; approve release; send; or publish.

