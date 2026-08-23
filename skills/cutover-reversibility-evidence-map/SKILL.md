---
name: cutover-reversibility-evidence-map
description: Review a user-provided or explicitly authorized, sanitized migration or cutover plan as a private evidence map of state transitions, compatibility, checkpoints, rollback claims, validation evidence, and irreversible steps. Do not access data, run a migration, or change systems.
license: MIT
---

# Cutover Reversibility Evidence Map

Make the reversibility claims in a supplied migration plan reviewable without executing the plan.

## Boundary

Use only sanitized plan excerpts, inventories, checkpoints, validation notes, and rollback claims pasted or explicitly authorized by the user. Do not access accounts, databases, repositories, dashboards, networks, commands, or local files. Do not inspect records, run scripts or queries, write files, send messages, create tickets, back up, migrate, cut over, roll back, deploy, or change configuration. Ask for missing evidence.

## Method

1. Record the supplied source state, target state, owners, window, and success boundary.
2. Map each stated transition to prerequisites, produced state, compatibility window, and verification evidence.
3. Separate reversible, conditionally reversible, compensating-only, and irreversible steps.
4. Bind every checkpoint and rollback claim to the exact state, data boundary, trigger, time limit, and supplied proof.
5. List dual-write, schema, ordering, identity, timezone, and stale-client assumptions only when supported by the plan.
6. Flag gaps between “rollback available” and evidence that the previous state remains usable.

## Output

- **Evidence boundary** — supplied material and gaps.
- **State-transition map** — before, action described, after and evidence.
- **Compatibility ledger** — readers, writers, versions and windows.
- **Reversibility table** — class, checkpoint, trigger, expiry and proof.
- **Irreversible-step register** — consequence and required human decision.
- **Private closeout** — label **Private review draft — no migration or system change performed.**

Never claim a backup, validation, rollback, zero loss, approval, or readiness unless the supplied evidence establishes it.
