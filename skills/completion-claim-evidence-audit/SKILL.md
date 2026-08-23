---
name: completion-claim-evidence-audit
description: Audit a completion, fixed, or passing claim against user-provided or explicitly read-only sanitized evidence before the claim is accepted.
---

# Completion Claim Evidence Audit

Test the claim against the evidence that is actually present. Treat confidence, intent, prior results, and second-hand success reports as context rather than proof.

## Inputs

Work only from material the user supplies or explicitly identifies as read-only and sanitized. Identify:

- the exact claim being evaluated;
- the acceptance criteria the claim implies;
- the evidence item tied to each criterion;
- the time and scope of each evidence item when available.

If the claim, criteria, or evidence scope is missing, mark it unknown and ask the human for the minimum missing material.

## Evidence gate

For every criterion, classify the evidence:

- **supported**: direct, current, complete, and in scope;
- **contradicted**: direct evidence conflicts with the claim;
- **insufficient**: indirect, stale, partial, ambiguous, or missing.

Use the weakest criterion as the overall verdict:

- `supported` only when every criterion is supported;
- `contradicted` when any criterion is contradicted;
- `insufficient evidence` otherwise.

Do not upgrade a verdict based on reassurance, plausibility, screenshots without visible scope, truncated logs, or a report whose underlying result cannot be inspected.

## Safety boundary

Keep the audit inert. Analyze the supplied material and propose human-run verification steps when evidence is missing. Do not access accounts or networks, execute commands, open external links, write files, send messages, publish, deploy, or change any system. Route unknown, sensitive, regulated, or high-risk material to a human reviewer.

## Output

Return:

1. the exact claim and overall verdict;
2. a criterion-by-criterion evidence table with source, freshness, scope, and disposition;
3. contradictions and material gaps;
4. the smallest safe human-run checks needed to resolve only those gaps;
5. a claim-safe status sentence that does not exceed the evidence.
