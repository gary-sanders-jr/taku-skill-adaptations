---
name: runbook-evidence-gap-review
description: Review a sanitized runbook or explicitly selected read-only runbook file and produce a private evidence-gap report. Use when someone wants to check whether an existing alert, on-call, or recovery procedure is clear and review-ready without executing it.
license: MIT
---

# Runbook Evidence Gap Review

Review only the runbook text the user supplies in the conversation or an explicitly selected read-only file. Return a private draft; do not operate the procedure.

## Intake boundary

Ask for the intended alert or symptom, audience, and supplied runbook. Encourage removal of secrets, personal data, live hostnames, credentials, and customer details. If the material is missing, ambiguous, sensitive, or consequential, identify the gap and hand the decision to the accountable human.

Do not access accounts, repositories, networks, dashboards, logs, terminals, ticketing systems, deployment systems, or production services. Do not run or test commands, links, queries, scripts, examples, alerts, mitigations, recovery steps, or escalation paths. Do not create, edit, or write files; send messages; publish; deploy; purchase; delete; change configuration; or perform any other external action.

## Review method

1. Record the supplied scope and label every observation as `observed`, `inferred`, or `unknown`.
2. Check whether the opening states the trigger, impact, immediate safe objective, owner, and last-review date.
3. Walk each branch as text. For every step, note prerequisites, expected result, failure branch, stop condition, rollback or containment note, and escalation trigger when these are explicitly supplied.
4. Flag vague verbs, missing thresholds, unexplained names, contradictions, unreachable branches, branches without a terminal outcome, and claims that lack supplied evidence.
5. Separate verification status from writing quality. Never claim a command, endpoint, mitigation, owner, threshold, contact, or recovery path works unless current authoritative evidence was supplied.
6. Rank gaps by reader harm: stranded responder, unsafe ambiguity, missing escalation, stale ownership, then readability.

## Output

Return:

- scope and evidence boundary;
- a short readiness status: `review-ready`, `needs-evidence`, or `human-escalation-required`;
- findings with location, observed text, gap, consequence, and a non-executed rewrite suggestion;
- branch-coverage and escalation checklists;
- contradictions and unknowns;
- questions for the runbook owner;
- a reminder that all commands and operational claims remain unverified until an accountable human validates them in an authorized environment.

Never convert absence of evidence into approval. Unknown or high-risk operational decisions belong to the responsible human.
