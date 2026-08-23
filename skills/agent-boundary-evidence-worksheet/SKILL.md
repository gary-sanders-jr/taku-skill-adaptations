---
name: agent-boundary-evidence-worksheet
description: Turn user-provided or explicitly authorized, sanitized agent-idea notes into a private worksheet covering user jobs, triggers, supplied inputs, observable end states, non-goals, worst plausible outcomes, success evidence, and open assumptions. Do not build, configure, or deploy an agent.
license: MIT
---

# Agent Boundary Evidence Worksheet

Create a private, reviewable boundary worksheet from supplied agent-idea evidence.

## Safety boundary

Use only material the user pasted, described, or explicitly authorized as a sanitized read-only artifact. Do not access accounts, dashboards, repositories, networks, commands, or local files. Do not write files, send messages, create tickets, choose tools or models, configure permissions, build, test, publish, deploy, or operate an agent. Do not invent stakeholders, baselines, authority, measurements, or approvals.

The result is a private review draft for an authorized human, not an implementation spec or permission grant.

## Method

1. Record who is on the other side, what they already have, what process is being replaced, the worst plausible outcome, and how value would be judged. Mark absent evidence explicitly.
2. Draft three to seven user-side jobs. For each, show its trigger, supplied input, and observable end state.
3. Separate plausible deferred non-goals from permanent boundaries. Include the supplied worst plausible outcome in the permanent boundary section.
4. Map each supplied success claim to a number, comparison, or named human judgment. Label slogans and unsupported targets as gaps.
5. List assumptions where a reasonable reviewer could disagree. Do not resolve them without user evidence.
6. Check whether following the worksheet could still authorize the wrong job or cross a stated boundary.

## Output

- **Evidence boundary** — supplied material and authorization.
- **Context ledger** — counterpart, existing process, baseline, worst plausible outcome, value test.
- **Job table** — job, trigger, supplied input, observable end state.
- **Not yet / Never** — plausible exclusions with reasons.
- **Success-evidence map** — claim, measure or judge, supplied evidence, gap.
- **Open assumptions** — human decisions still required.
- **Private closeout** — label **Private review draft — no agent changes performed.**

Never claim that the agent is scoped, approved, safe, build-ready, or production-ready unless the supplied evidence explicitly establishes that conclusion.
