---
name: dependency-upgrade-compatibility-evidence-map
description: Review user-provided or explicitly authorized, sanitized dependency-upgrade notes as a private map of version intent, compatibility claims, breaking changes, transitive assumptions, validation evidence, and rollback limits. Do not inspect repositories, install packages, or change dependencies.
license: MIT
---

# Dependency Upgrade Compatibility Evidence Map

Make the evidence behind a proposed dependency change reviewable without touching a project or package registry.

## Boundary

Use only sanitized version lists, release-note excerpts, compatibility statements, test summaries, and rollback notes pasted or explicitly authorized by the user. Do not access accounts, repositories, registries, networks, commands, or local files. Do not resolve versions, fetch advisories, install packages, edit manifests or lockfiles, run tests, write files, send messages, create tickets, merge, publish, deploy, or roll back. Ask for missing evidence.

## Method

1. Record the supplied package, current version, target version, runtime, platform, and upgrade intent.
2. Separate direct and transitive dependency claims; mark unknown resolution and lockfile effects.
3. Map supplied release-note or compatibility statements to the exact affected surface and version interval.
4. Record breaking-change, peer-range, runtime, build-tool, data-format, and license assumptions only from supplied material.
5. Bind each validation claim to the supplied command description, scope, environment, outcome, and untested surface without running it.
6. Classify rollback as exact, conditional, compensating-only, or unproven and record irreversible state changes.

## Output

- **Evidence boundary** — supplied material and gaps.
- **Version intent** — current, target, range, resolver and platform.
- **Compatibility map** — surface, claim, evidence and uncertainty.
- **Transitive-assumption ledger** — dependency, expected effect and proof gap.
- **Validation coverage** — supplied checks and untested surfaces.
- **Private closeout** — label **Private review draft — no dependency or project change performed.**

Never claim compatibility, security, license clearance, successful tests, rollback, approval, or release readiness unless the supplied evidence establishes it.
