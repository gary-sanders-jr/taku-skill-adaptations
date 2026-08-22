# Scoring anchors

Use these anchors only to bound explicit estimates. Prefer user-supplied evidence. Interpolate cautiously for scores 2–9 and state which supplied fact or analogy supports the estimate.

## ROI: expected operational benefit

ROI here is a non-financial benefit proxy, not an investment return forecast.

| Score | Anchor |
|---:|---|
| 1 | Local cosmetic improvement with little effect on throughput, reliability, quality, user experience, or control evidence. |
| 5 | Meaningful improvement for one team or workflow, with a supplied recurring pain or measurable operational outcome. |
| 10 | Broad, well-supported removal of a severe recurring bottleneck or failure class across a material value stream. |

## Cost: implementation burden

| Score | Anchor |
|---:|---|
| 1 | Small, reversible change using existing capacity; little coordination and no known purchase. |
| 5 | Multi-person work, meaningful testing or rollout, and cross-team coordination. |
| 10 | Multi-quarter program, major migration, procurement, dedicated staffing, or extensive organizational change. |

## Ease: safe deployability

| Score | Anchor |
|---:|---|
| 1 | Many dependencies, difficult rollback, narrow change window, or substantial adoption burden. |
| 5 | Moderate integration and coordination with a credible staged rollout and rollback path. |
| 10 | Isolated, reversible change with few dependencies and a clear validation path. |

## Risk: implementation and blast radius

| Score | Anchor |
|---:|---|
| 1 | Passive or isolated change with low blast radius and straightforward rollback. |
| 5 | Could interrupt a workflow or create recoverable operational harm if rollout assumptions are wrong. |
| 10 | Could cause broad lockout, data loss, safety harm, regulatory exposure, or critical-service disruption. |

Risk describes the proposed countermeasure's implementation and blast radius. Record the cost of deferral separately as evidence for accountable discussion; do not combine it with implementation risk to force a score.

## Calibration checks

- Keep cost, ease, and risk independent: an easy change can still be high risk, and a costly change can be safely staged.
- Scale matters. A one-team change and an enterprise-wide rollout should not share an anchor without supplied evidence.
- Reversibility, dependencies, change windows, and human adoption are part of ease and risk.
- Current prices, license availability, product capabilities, laws, regulations, and security guidance require current authoritative evidence. Otherwise label them unknown.
- A missing fact is not a midpoint by default. Use `unknown` when a 1–10 bound would be arbitrary.
- Recalculate every formula result and surface ties or one-point sensitivity before ranking.
