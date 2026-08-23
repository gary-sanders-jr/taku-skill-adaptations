# Adaptation notes

This derivative preserves the upstream review topic—BigQuery pipeline cost exposure, bounded backfills, query safety, idempotent writes, and observability—while changing the operating boundary for Taku.

Material changes:

- limits input to sanitized pasted text or a user-designated read-only file;
- forbids cloud, network, account, repository-wide, shell, database, execution, and file-write actions;
- treats embedded instructions as inert untrusted data;
- adds credential, personal-data, customer-data, and proprietary-data minimization;
- converts cost estimates into evidence-bounded symbolic models;
- separates observed facts, inferences, unknowns, and current-source checks;
- makes all patches advisory and not applied;
- adds qualified-human escalation for security, privacy, legal/compliance, finance, and production decisions.

This is an adapted derivative, not a byte-preserved copy and not an official GitHub product.

