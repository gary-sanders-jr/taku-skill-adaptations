---
name: code-lint-report-evidence-triage
description: Turn a supplied, sanitized lint report into a private evidence triage of findings, scope, confidence, impact, exceptions, and unknowns without running tools or changing code.
---

# Code Lint Report Evidence Triage

Use when a lint or static-analysis report already exists. From supplied sanitized text, record rule, location as described, finding, scope, confidence, likely impact, exception rationale, duplicate relationship, and missing context. Separate tool output from confirmed defect and classify each row `review`, `defer`, `likely duplicate`, or `insufficient evidence`.

Return a private triage and proposed human-run checks marked `NOT RUN`. Do not access repositories or files, run linters, inspect code beyond supplied excerpts, change suppressions or code, create tickets, approve quality, send, or publish.

