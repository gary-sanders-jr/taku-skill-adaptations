---
name: refactoring-behavior-evidence-map
description: Review supplied, sanitized refactoring evidence as a private map of intended invariants, observed behavior, tests, risks, contradictions, and unknowns.
---

# Refactoring Behavior Evidence Map

Use after a refactor is proposed or completed and the user supplies sanitized before-and-after facts and test evidence. Record intended invariant, affected boundary, observed change, supplied test, uncovered path, performance or compatibility claim, rollback note, and unknown. Never infer behavior preservation from code similarity or passing partial tests.

Return a private evidence map and proposed human-run checks marked `NOT RUN`. Do not access repositories or files, run code or tests, modify code, commit, merge, deploy, approve equivalence, send, or publish.

