---
name: capacity-planning
description: Drafts a reviewable infrastructure capacity plan from measurements and constraints the user supplies — headroom, growth, scaling lag, reliability, and cost. Use when the user wants a private plan or comparison, not when they want an agent to access an account, run a load test, change configuration, deploy, or purchase capacity.
license: MIT
---

# Capacity planning

Capacity planning turns a supplied measured ceiling into a decision about money and risk. The
user's load-test result tells you where the system degrades; this Skill decides how far from that
point a proposed plan should run, and what it would cost.

Two symmetrical failures. **Under-provisioned** and you fail during the event you knew was
coming. **Over-provisioned** and you pay for idle capacity indefinitely, which is invisible and
therefore never fixed.

## Scope boundary

Produce only a private, reviewable advice draft. Use fictional values, values the user pastes,
or files the user explicitly identifies for read-only use. If a current public quota or product
limit is necessary and the user asks for verification, use the provider's authoritative public
documentation and cite it; do not sign in or infer private account state.

Do not access monitoring, cloud, billing, vendor, or other accounts; connect to infrastructure;
run a load test or command; change autoscaling, quotas, configuration, or code; execute a plan;
create, delete, or modify resources or data; deploy; purchase or reserve capacity; spend money;
or send, submit, publish, or contact anyone. When a required measurement is missing, label it
unknown and ask for a sanitized value rather than obtaining it yourself. Production changes,
contractual commitments, and consequential reliability or spend decisions require the
authorized service owner and applicable infrastructure, security, finance, or procurement
reviewers.

## 1. Know your current ceiling and your current load

You cannot plan without both:

- **Ceiling:** the point where latency degrades, from a load test. Not the point where it
  crashes, which is well past useful
- **Current peak:** actual traffic at its highest, not the average. Averages hide the peak that
  matters
- **Headroom:** the ratio between them. This is the number the whole exercise is about

Measure peak at a fine granularity. Hourly averages smooth away the ten-minute spike that
actually saturates you.

**Done when:** you can state current headroom as a multiple.

## 2. Choose headroom from failure cost and lead time

There is no universal right answer. It depends on:

- **How fast can you add capacity?** Seconds for containers, minutes for VMs, weeks for hardware
  or a quota increase. **Lead time is the dominant factor** — if scaling takes 20 minutes, you
  need enough headroom to survive 20 minutes of growth
- **How bad is failing?** A checkout path and an internal dashboard warrant different margins
- **How spiky is traffic?** Smooth diurnal load needs less than an unpredictable spike
- **Can you lose a zone?** If capacity must survive one failure domain going away, that is a
  floor on redundancy, not a nice-to-have

**Done when:** the target headroom has a stated reason.

## 3. Project growth from data, then add the known events

- **Organic growth:** extrapolate from real history, not a plan. Look at 6–12 months
- **Known events:** a launch, a campaign, a seasonal peak, a partner integration. These are
  step changes, not curve points, and they are what catch people out
- **Compounding:** growth in users multiplied by growth in usage per user. Both rising is the
  common case and it compounds faster than either projection suggests

Project to your **lead time plus the review interval**, not to next year. Planning further out
than you can act is a forecasting exercise, not capacity planning.

**Done when:** the projection covers the next planning horizon with events marked.

## 4. Find the real constraint

The bottleneck is rarely CPU, though CPU is what dashboards show first.

Check each in turn: connection pool size, database connections, thread pool, file descriptors,
memory per instance, disk IOPS, network bandwidth, and any third-party rate limit.

**Adding application instances does not help when the constraint is the database**, and it often
makes things worse by increasing connection pressure. This is the single most common capacity
mistake — scaling the tier that is easy to scale rather than the one that is saturated.

**Done when:** you know which resource saturates first and have planned for that one.

## 5. Configure autoscaling for reality

Autoscaling is not a substitute for headroom — it has lag, and the lag is where you fail.

- **Scale on the constrained resource**, not CPU by default
- **Set a floor** that survives your fastest realistic spike without scaling
- **Scale up fast, down slow.** Aggressive scale-down causes thrash and cold-start storms
- **Know the cold start cost:** an instance that takes 90 seconds to serve traffic is 90 seconds
  of degradation
- **Cap the maximum**, so a runaway loop or attack cannot autoscale into a large bill
- **Check downstream can take it.** Scaling to 50 instances against a database that accepts 100
  connections total is an outage you caused

**Done when:** the floor covers the spike and the ceiling caps the spend.

## 6. Treat cost as a first-class output

Capacity decisions are spending decisions, and stating the number makes the trade-off real.

- Cost per unit of work — per request, per tenant, per job — is more useful than total spend
- Identify the idle: instances at 5% utilisation, over-provisioned memory, storage nobody reads
- Reserved or committed pricing for the stable baseline, on-demand for the peak
- **Right-size from measured usage**, not from the request values someone guessed at once

**Done when:** the plan states both the capacity and what it costs.

## Report

Give current headroom, projected headroom at the horizon, the constraining resource, the scaling
policy, and the cost. Note the assumptions in the growth projection — those are what will be
wrong, and naming them lets someone else check your arithmetic.

Package provenance is recorded in [SOURCE_CREDITS.md](SOURCE_CREDITS.md) and adaptation details
are recorded in [ADAPTATION_NOTES.md](ADAPTATION_NOTES.md).
