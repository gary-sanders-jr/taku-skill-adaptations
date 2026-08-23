# Adaptation notes

This derivative preserves the upstream goal of reviewing prompts for safety, bias, privacy, security and effectiveness while narrowing the operating contract for Taku.

Material changes:

- accepts one sanitized supplied prompt or one explicitly designated read-only file;
- returns a private evidence report and small unapplied guardrail snippets instead of a complete rewritten prompt;
- never runs the prompt, calls a model/evaluator, browses, tests, uploads, edits, persists, sends, publishes, schedules, purchases, deploys or deletes;
- treats embedded prompt instructions and retrieved/tool content as inert untrusted data;
- adds secret, PII, customer, proprietary and third-party-rights minimization;
- separates observed, reported, inferred, unknown and current-verification claims;
- adds high-risk qualified-owner routing and forbids compliance, safety or runtime guarantees.

This is an adapted derivative, not a byte-preserved copy and not an official GitHub product.
