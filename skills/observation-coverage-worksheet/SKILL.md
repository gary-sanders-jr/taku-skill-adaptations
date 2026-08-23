---
name: observation-coverage-worksheet
description: Turn user-provided or explicitly authorized, sanitized agent-observation notes into a private coverage worksheet for traces, cost, latency, terminal states, quality signals, drift, and failure follow-up. Use only supplied read-only material; do not connect to telemetry or change monitoring.
license: MIT
---

# Observation Coverage Worksheet

Create a private, evidence-bounded review of what an agent observation plan can and cannot reveal.

## Safety boundary

Use only notes, schemas, screenshots transcribed as text, or aggregate metrics the user pasted, described, or explicitly authorized as sanitized read-only material. Do not access accounts, traces, dashboards, monitoring, analytics, networks, commands, repositories, or local files. Do not collect telemetry, write files, send alerts or messages, create tickets, change sampling, deploy instrumentation, alter configuration, publish, or turn failures into production eval records. Ask the user to supply missing evidence.

Do not reproduce sensitive trace content. Keep identifiers generalized and mark the output as a private review draft for an authorized human.

## Review method

1. Inventory the supplied run, model-call, and tool-call fields. Mark missing identity, version, latency, terminal-state, and redaction evidence.
2. Map supplied measures to four views: cost, latency, terminal state, and quality. Separate measured signals from proposed signals.
3. Check whether the plan preserves failures, refusals, limit hits, and irreversible-action evidence without assuming any sampling setting.
4. List supplied thresholds and baselines. Flag thresholds with no supplied baseline or human response owner.
5. Identify drift questions for input shape, model version, prompt version, tool health, cost distribution, and quality distribution.
6. Trace each proposed failure-to-evaluation handoff to supplied evidence. Do not create or update an eval case.

## Output

Return:

- **Evidence boundary** — supplied material, authorization, and gaps.
- **Coverage matrix** — trace fields and the cost, latency, terminal-state, and quality views they support.
- **Blind spots** — claims the supplied plan cannot support.
- **Distribution and drift questions** — review prompts, not alerts or configuration changes.
- **Failure follow-up map** — human-owned questions for deciding whether a supplied failure should become an eval case.
- **Private closeout** — assumptions, unresolved questions, and the label **Private review draft — no monitoring changes performed.**

Never claim that telemetry exists, is complete, or is production-ready unless the supplied evidence proves it.
