---
name: metric-claim-boundary-map
description: Turn user-provided or explicitly authorized, sanitized aggregate metrics and analysis notes into a private map of metric definitions, populations, periods, comparisons, caveats, and claims the evidence does not support. Do not query data sources or compute from private datasets.
license: MIT
---

# Metric Claim Boundary Map

Create a private, evidence-bounded interpretation of supplied aggregate metrics without turning association into causation.

## Safety boundary

Use only aggregate numbers, definitions, and analysis notes the user pasted, described, or explicitly authorized as sanitized read-only material. Do not access accounts, databases, spreadsheets, dashboards, analytics, networks, commands, or local files. Do not run queries, inspect raw rows, write files, send messages, create tickets, publish, change instrumentation, or make business decisions. Ask the user for missing evidence.

Do not infer excluded populations, date boundaries, timezones, data quality, statistical significance, causation, or authorization. The output is a private review draft for an authorized human.

## Method

1. Record the supplied metric definition, population, exclusions, grain, period, timezone, comparison, and intended decision. Mark gaps.
2. List supplied evidence about coverage, missingness, duplicates, test accounts, gaps, spikes, and distribution shifts. Do not claim checks were run.
3. Check whether the comparison is like-for-like and whether denominators, seasonality, or segment mix differ in the supplied notes.
4. Separate observation, association, and causal claim. Remove or flag causal language unsupported by supplied controls.
5. Record small-sample, survivorship, multiple-comparison, aggregation, and Simpson’s-paradox risks only when relevant to the supplied facts.
6. Pair every reported number with exclusions, segmentation, caveats, and what the evidence cannot establish.

## Output

- **Evidence boundary** — supplied inputs and gaps.
- **Metric contract** — definition, population, exclusions, grain, period, timezone, comparison.
- **Data-trust ledger** — supplied checks and unverified checks.
- **Comparison map** — numerator, denominator, baseline, segment and seasonality notes.
- **Claim boundary table** — supplied wording, evidence level, safe wording, unsupported leap.
- **Private closeout** — label **Private review draft — no data-source access or business action performed.**

Never claim the result is statistically valid, causal, complete, reproducible, approved, or decision-ready unless the supplied evidence proves each claim.
