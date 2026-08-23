---
name: capacity-assumption-ledger
description: Turn user-provided or explicitly authorized, sanitized capacity-planning notes into a private ledger of demand, supply, headroom, constraints, assumptions, confidence, and unsupported conclusions. Do not inspect systems, forecast from private telemetry, or change capacity.
license: MIT
---

# Capacity Assumption Ledger

Build a reviewable capacity argument from supplied aggregate facts without operating infrastructure.

## Boundary

Use only sanitized aggregate demand, supply, utilization, growth, seasonality, and constraint notes pasted or explicitly authorized by the user. Do not access accounts, dashboards, monitoring, cloud consoles, repositories, networks, commands, or local files. Do not query telemetry, calculate from raw events, write files, send messages, create tickets, purchase resources, change limits, scale, deploy, or approve a capacity decision. Ask for missing evidence.

## Method

1. Record the supplied service boundary, unit, period, peak window, population, and decision horizon.
2. Separate demand evidence from supply evidence; preserve each supplied unit and timestamp.
3. List headroom formulas exactly as supplied or show transparent arithmetic from supplied aggregate numbers.
4. Record seasonality, burst, dependency, quota, failure-mode, and recovery assumptions with an owner and confidence label when provided.
5. Pair each conclusion with supporting facts, contrary facts, and evidence gaps.
6. Flag unit mismatches, averages used for peaks, double-counted redundancy, and forecasts without a stated method.

## Output

- **Evidence boundary** — supplied inputs and gaps.
- **Demand ledger** — baseline, peak, growth, burst and seasonality.
- **Supply ledger** — usable capacity, bottlenecks, quotas and dependencies.
- **Headroom table** — formula, inputs, result and uncertainty.
- **Assumption register** — assumption, evidence, confidence, owner and falsifier.
- **Private closeout** — label **Private review draft — no system access or capacity action performed.**

Never claim a forecast, purchase, scale action, resilience level, approval, or decision readiness unless the supplied evidence establishes it.
