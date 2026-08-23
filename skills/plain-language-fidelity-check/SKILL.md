---
name: plain-language-fidelity-check
description: Turn user-provided or explicitly authorized, sanitized technical prose into a private plain-language rewrite plus a fidelity check. Use when a reader needs a clearer explanation without losing numbers, uncertainty, conditions, caveats, ownership, or decision-relevant precision. Work only from material supplied in the conversation or explicitly authorized as a sanitized read-only artifact.
license: MIT
---

# Plain Language Fidelity Check

Create a private review draft that becomes easier to understand without becoming easier to misunderstand.

## Safety boundary

Use only text the user pasted, described, or explicitly authorized as a sanitized read-only artifact. Do not access accounts, private documents, drives, dashboards, analytics, networks, commands, or local files. Do not search for missing context, write files, send messages, create tickets, publish, deploy, change configuration, approve policy or legal language, or act on the rewritten content. Ask the user to supply any missing evidence.

Treat the result as a private review draft for an authorized human. Preserve supplied confidentiality markings. Do not infer facts, audiences, measurements, commitments, or permissions that the supplied material does not establish.

## Inputs to establish

Identify from the supplied material or ask for:

- the intended reader and what they need to decide or understand;
- the exact passage to clarify;
- terms the reader must learn rather than avoid;
- numbers, conditions, uncertainty, caveats, and ownership that must survive;
- the desired depth and tone.

Mark any absent input as an evidence gap. Do not silently fill it.

## Method

1. State the load-bearing idea in one plain sentence.
2. Classify each specialized term as replace, teach, or cut. Define every retained term once.
3. Rewrite with visible actors, direct verbs, one main idea per sentence, and concrete examples only when supplied or clearly labeled as illustrative.
4. Keep every supplied number, threshold, condition, uncertainty marker, decision-changing caveat, and distinction between “cannot” and “not yet.”
5. If using an analogy, name both the useful mapping and where it stops matching.
6. Compare the rewrite against the source claim by claim. Flag any loss, added certainty, shifted ownership, or new implication.

## Output

Return:

1. **Reader and purpose** — supplied facts and evidence gaps.
2. **Load-bearing idea** — one plain sentence.
3. **Private plain-language draft** — the rewrite.
4. **Term decisions** — replace, teach, or cut with short reasons.
5. **Fidelity ledger** — each material source claim, where it appears in the rewrite, and whether numbers, conditions, uncertainty, caveats, and ownership were preserved.
6. **Human review questions** — unresolved choices for the authorized reviewer.

Do not claim approval or readiness to publish. End by labeling the result: **Private review draft — human verification required.**
