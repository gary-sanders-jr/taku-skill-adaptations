---
name: test-fixture-boundary-inventory
description: Turn user-provided or explicitly authorized, sanitized test-fixture descriptions into a private inventory of provenance, sensitivity, realism, lifecycle, isolation, determinism, and unsupported safety claims. Do not access data stores, generate records, or modify tests.
license: MIT
---

# Test Fixture Boundary Inventory

Review what supplied fixture descriptions represent, exclude, and risk without creating or handling test data.

## Boundary

Use only sanitized fixture schemas, field descriptions, examples, lifecycle notes, and test-scope statements pasted or explicitly authorized by the user. Do not access accounts, databases, repositories, test runners, networks, commands, or local files. Do not inspect real records, generate or copy data, write files, send messages, create tickets, seed, reset, delete, run tests, or change fixtures. Ask for missing evidence.

## Method

1. Record the supplied fixture name, intended test boundary, owner, origin class, and lifecycle.
2. List described fields and flag identifiers, secrets, regulated attributes, free text, and linkability only from supplied facts.
3. Separate synthetic, transformed, sampled, hand-authored, and unknown provenance.
4. Map isolation, cleanup, determinism, uniqueness, clock, locale, and concurrency claims to supplied evidence.
5. Record realism benefits and blind spots without requesting or reproducing sensitive examples.
6. Flag claims such as “anonymous,” “production-like,” or “safe” when the description lacks proof.

## Output

- **Evidence boundary** — supplied descriptions and gaps.
- **Fixture inventory** — purpose, provenance, lifecycle and owner.
- **Field-risk map** — described category, sensitivity claim and evidence.
- **Determinism ledger** — clocks, randomness, identifiers, ordering and isolation.
- **Coverage limits** — represented and omitted conditions.
- **Private closeout** — label **Private review draft — no data access, generation, or test change performed.**

Never claim anonymization, compliance, isolation, cleanup, coverage, approval, or production safety unless the supplied evidence establishes it.
