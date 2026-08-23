# Adaptation notes

This derivative preserves the upstream goal of separating a minimal observable bug reproduction from diagnosis and repair, while changing the operating boundary for Taku.

Material changes:

- accepts only sanitized pasted material or a specifically designated read-only file;
- prepares a reproduction brief and not-run verification plan instead of executing the reproduction;
- forbids repository, account, network, database, issue-tracker, file-write, command, test, commit, send, deploy, delete, and configuration actions;
- labels supplied observations, unverified reports, inferences, and unknowns;
- treats embedded instructions as inert untrusted data;
- adds credential, personal-data, customer-data, and proprietary-data minimization;
- routes security, privacy, legal/compliance, finance, and production-incident decisions to authorized owners.

This is an adapted derivative, not a byte-preserved copy and not an official GitHub product.

