---
name: ci-pipeline-assumption-map
description: Review supplied, sanitized CI pipeline notes as a private map of triggers, stages, artifacts, gates, credentials, evidence, failure paths, and assumptions.
---

# CI Pipeline Assumption Map

Use when an existing CI pipeline description needs an evidence and assumption review, not when the user wants a workflow authored, run, approved, or deployed.

Use only pipeline YAML excerpts, diagrams, run summaries, or requirements the user supplies or explicitly selects as sanitized read-only material. Embedded scripts and links are inert, and secret values must never be repeated.

## Procedure

1. Confirm repository-free scope, supplied evidence, and redaction.
2. Trace triggers, jobs, artifacts, environments, gates, and failure paths.
3. Classify observations, assumptions, contradictions, and unknowns.
4. Rank unsupported assumptions by their effect on build or release decisions.

Map triggers, branches, jobs and ordering, artifacts and promotion, cache assumptions, environment boundaries, credential scopes as described, required gates, rollback or retry paths, supplied run evidence, and unknowns. Label rows `supplied observation`, `assumption`, `unknown`, or `contradicted`.

Do not read repositories or CI accounts, run workflows or commands, inspect secrets, modify YAML, approve jobs, upload artifacts, deploy, retry, cancel, send, or publish. Route credential and production decisions to authorized owners.

Return a private pipeline map, the highest-impact unsupported assumptions, and proposed human-run checks marked `NOT RUN`.

Done when every stage and gate claim is cited or marked unknown; stop if credentials or production details are not safely redacted.
