# Adaptation notes

This derivative preserves the upstream goal of PostgreSQL-specific review while changing the operating contract for Taku.

Material changes:

- accepts only sanitized pasted text or one explicitly designated read-only file;
- produces a private evidence report and unapplied suggestions, never database or repository action;
- forbids connections, SQL/EXPLAIN execution, commands, tests, migrations, file edits, ticket/account operations, sends, grants, deploys, deletes and configuration changes;
- adds secret, PII, customer-row and proprietary-code minimization plus inert-data handling;
- distinguishes observed, reported, inferred, unknown and version-sensitive claims;
- treats performance, locking and migration conclusions as hypotheses unless directly evidenced;
- routes security, privacy, compliance, incident and production decisions to authorized qualified owners.

This is an adapted derivative, not a byte-preserved copy and not an official GitHub product.
