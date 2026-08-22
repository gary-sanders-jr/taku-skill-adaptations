# Power BI semantic-model review framework

Use this checklist selectively. Mark an item `not supplied` rather than assuming a pass or failure.

## Schema architecture

- Fact tables have an explicit and consistent grain.
- Dimensions contain descriptive attributes at a compatible grain.
- Primary, surrogate, natural, and foreign-key roles are distinguishable.
- Many-to-many relationships and bridge tables have a stated business need.
- Snowflaking, denormalization, and role-playing dimensions have a stated rationale.
- Names, data types, formatting, descriptions, and hidden technical fields are coherent.

## Relationships

- Cardinality is supported by the supplied key evidence.
- Filter direction is intentional and avoids ambiguous propagation paths.
- Active and inactive relationships support the intended calculations.
- Orphans, unknown members, blank rows, and referential-integrity assumptions are addressed.
- Text or high-cardinality relationship keys have a documented tradeoff.

## Storage and refresh

- Import, DirectQuery, Dual, Hybrid, or composite choices match supplied freshness and scale constraints.
- Cross-source relationships and aggregations have explicit assumptions.
- Incremental refresh partitions and historical windows match the user's stated needs.
- Refresh, capacity, concurrency, gateway, and source constraints are evidence-backed.

## Calculations and performance

- Measures and calculated columns are used intentionally.
- Supplied DAX has clear context, filters, variables, and error behavior.
- High-cardinality columns and unused attributes are candidates for measured review.
- Iterators, context transitions, bidirectional filters, and many-to-many paths are hypotheses for testing, not automatic defects.
- Any claimed benefit includes a baseline and an authorized validation method.

## Maintainability

- Tables, columns, measures, relationships, and business rules are described.
- Display folders and naming conventions support discovery.
- Ownership, test evidence, change review, rollback, and version context are known.
- Source lineage and transformation responsibilities are distinguishable from model logic.

## Security and governance

- RLS and object-level security intent, role mapping, and test ownership are explicit.
- Sensitive data is classified according to the user's current approved policy.
- Privacy, retention, access review, audit, and regulatory questions are sent to accountable owners.
- No checklist result is presented as a security or compliance certification.

## Priority rubric

Prioritize with evidence, not invented scores:

1. **Now** — supplied evidence indicates a material correctness, access, or operational concern requiring human review before the next authorized change.
2. **Next** — a meaningful maintainability, scalability, or performance hypothesis with a feasible validation step.
3. **Later** — cleanup or enhancement that is useful but not supported as urgent.

For every priority, include confidence, missing evidence, an alternative explanation, a reversible validation step, and the accountable human role.
