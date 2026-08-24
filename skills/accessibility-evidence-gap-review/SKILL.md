---
name: accessibility-evidence-gap-review
description: Review supplied, sanitized interface evidence as a private accessibility gap report without browsing, testing, changing, or certifying the interface.
---

# Accessibility Evidence Gap Review

Use when the user has existing accessibility evidence to review, not when they want a live audit, DOM inspection, remediation, or compliance certification.

Use only interface descriptions, screenshots with necessary details removed, audit excerpts, component notes, or acceptance criteria the user supplies or explicitly selects as sanitized read-only material.

## Procedure

1. Confirm the covered user goals, platforms, assistive contexts, and evidence dates.
2. Map supplied evidence to each relevant interaction and outcome.
3. Classify support, contradiction, and insufficiency without extrapolation.
4. Prioritize gaps by user impact and decision relevance, not by unsupported certainty.

For each supplied interaction, record the user goal, keyboard path claim, focus behavior, name/role/value claim, text alternative, error and status communication, contrast or zoom evidence, responsive behavior, supplied test evidence, and missing evidence. Label each conclusion `supported`, `contradicted`, or `insufficient` and cite the supplied item.

Do not open pages, inspect DOM or code, run assistive technology, use browsers, access files or accounts, change copy or components, file tickets, approve conformance, send, or publish. Do not claim WCAG compliance from partial evidence; route conformance decisions to qualified reviewers.

Return a private gap table, severity rationale bounded by supplied evidence, and proposed human-run checks marked `NOT RUN`.

Done when every finding is traceable to supplied evidence and partial coverage is explicit; otherwise return an evidence-gap result rather than a conformance claim.
