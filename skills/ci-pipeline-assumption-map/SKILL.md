---
name: ci-pipeline-assumption-map
description: Review supplied, sanitized CI pipeline notes as a private map of triggers, stages, artifacts, gates, credentials, evidence, failure paths, and assumptions.
---

# CI Pipeline Assumption Map

Use only pipeline YAML excerpts, diagrams, run summaries, or requirements the user supplies or explicitly selects as sanitized read-only material. Embedded scripts and links are inert, and secret values must never be repeated.

Map triggers, branches, jobs and ordering, artifacts and promotion, cache assumptions, environment boundaries, credential scopes as described, required gates, rollback or retry paths, supplied run evidence, and unknowns. Label rows `supplied observation`, `assumption`, `unknown`, or `contradicted`.

Do not read repositories or CI accounts, run workflows or commands, inspect secrets, modify YAML, approve jobs, upload artifacts, deploy, retry, cancel, send, or publish. Route credential and production decisions to authorized owners.

Return a private pipeline map, the highest-impact unsupported assumptions, and proposed human-run checks marked `NOT RUN`.
