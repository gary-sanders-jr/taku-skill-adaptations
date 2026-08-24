---
name: load-test-result-evidence-audit
description: Audit supplied, sanitized load-test results as a private report of workload, saturation, latency, errors, limits, caveats, and unsupported claims.
---

# Load Test Result Evidence Audit

Use after a load test has already been run and the user supplies sanitized results. Do not use it to design, start, or control a load test.

Record the stated workload model, duration, concurrency or arrival rate, environment, data shape, warm-up, measured percentiles, throughput, errors, saturation signals, limits, exclusions, and comparison baseline. Preserve units, denominators, timestamps, and scope.

For every conclusion, classify the supplied evidence as `supported`, `contradicted`, or `insufficient`. Flag coordinated-omission risk, mixed populations, truncated windows, unstable warm-up, unreported errors, or production-readiness claims that exceed the evidence.

Return a private audit, safe claim wording, and proposed human-run checks marked `NOT RUN`.

Do not access load generators, dashboards, clouds, files, repositories, networks, accounts, billing, or monitoring; run queries or tests; change capacity; approve readiness; send; or publish.

