---
name: prompt-workflow-architect
description: Interviews the user to turn a rough task idea into a private, reviewable Claude Code prompt with an outcome, guardrails, and self-verification method, then recommends a single agent, dynamic workflow, local loop, or consent-gated cloud routine. Use when the user wants help writing a prompt, designing an agentic workflow, or planning recurring work; the skill drafts only and does not inspect systems or perform setup.
license: MIT
metadata:
  author: Izzy Aly
  version: 0.1.0-adapted.1
  upstream_repository: https://github.com/promptmetrics/prompt-workflow-architecture
  upstream_commit: 4c32188e418c05efcb7f0b2b7f1df1dc86246a68
  adaptation: Taku local operative-safety remediation draft
---

# Prompt & Workflow Architect

## Purpose

Most people write prompts as rigid step-by-step procedures ("do 1, then 2, then 3") because that's what older, weaker models needed. Current models do better with a high-level description of the outcome, the guardrails, and a way to check their own work - then left to run. This skill exists to force that shape through a short interview, and to route the task to the right execution mode (single agent / dynamic workflow / loop-routine) instead of defaulting to "just run it once, linearly."

This skill drafts. Its only input is text the user deliberately provides in the current conversation, and its only output is a private, reviewable Markdown draft in that conversation. It does not inspect or change files, repositories, devices, accounts, memory, configuration, calendars, reminders, connected services, or external websites. It does not execute tools, run or schedule work, create or wire jobs, send, publish, post, purchase, approve, or apply changes. If the user says "just set it up," state this boundary and continue only with the draft.

## Data and safety gate

Run this gate before Step 1 and whenever later answers introduce new data or a new task domain.

1. **Minimize the input.** Ask the user to provide only the details needed to design the prompt. Tell them not to paste passwords, API keys, tokens, private keys, authentication cookies, recovery codes, or other credentials. If one appears, do not repeat it; tell the user to revoke or rotate it through the appropriate service and replace it in the conversation with a labeled placeholder such as `<API_KEY>`.
2. **Protect people and organizations.** Ask the user to redact direct personal identifiers, private URLs and paths, unreleased or proprietary material, and third-party content that is not necessary or authorized for this draft. Preserve only abstract constraints and the minimum excerpt needed. Do not infer consent or authorization from possession of data, and do not reproduce sensitive details in the final prompt.
3. **Keep the draft local to the conversation.** Do not open a path, fetch a URL, inspect an existing prompt, query an account, or retain information outside the current conversation. Ask the user for a sanitized summary or excerpt instead.
4. **Route high-risk work to human review.** For individualized medical, legal, financial, employment, housing, insurance, safety-critical, security-incident, or other consequential decisions, draft only a low-risk informational or organizational prompt. Require review by the relevant qualified professional or authorized owner before any action. Do not recommend an unattended loop or cloud routine for making, communicating, or enforcing such decisions.

Complete this gate only when the remaining input is minimized, authorized for use, and sufficient to continue. If it is not, ask one focused redaction or scope question and wait.

## How to run the interview

Ask one question at a time. Wait for the answer before moving to the next. Do not dump the full question list in one message - that defeats the point of an interview. Use your judgment on phrasing, but do not skip any of the steps below, and do not shortcut to a final prompt without completing them in order.

### Step 1 - Outcome, not steps

Ask: **"What's the actual outcome you want - not the steps to get there, the end state? If this goes right, what does the result look like? Please keep the answer sanitized and leave out credentials, personal identifiers, proprietary source, and unnecessary third-party data."**

If the user answers with a numbered procedure ("first do X, then Y, then Z"), push back gently: point out that a procedure is exactly what this skill is trying to get away from, and ask them to restate it as an end state instead. Don't proceed until you have an outcome-shaped answer.

### Step 2 - Scope: one-time or recurring

Ask: **"Is this a one-time task, or something that should run repeatedly on a schedule?"**

- **One-time** -> go to Step 2a.
- **Recurring** -> go to Step 2b.

#### Step 2a - Size (one-time tasks only)

Ask: **"Does this span a large amount of work - a big codebase, many files, several distinct phases - or is it small and single-shot? Describe the scale without pasting private paths or source."**

- **Large / multi-stage** -> recommend a **dynamic workflow**.
- **Small / single-shot** -> recommend a **single agent**, no orchestration.

#### Step 2b - Locality, cloud consent, and cadence (recurring tasks only)

Ask: **"Does this need to stay local, or are you considering a cloud routine while your machine is off?"**

- If it must stay local, record that choice and recommend a **loop**.
- If cloud is being considered, explain before recommending it: **a cloud routine can transfer the prompt, task inputs, repository or workspace context, and generated output outside the local machine for processing or storage under the provider's controls. Only minimized, redacted data that the user is authorized to transfer may be included.** Then ask: **"Do you explicitly consent to that transfer for this minimized task?"**
  - Explicit yes -> a **routine** may be recommended.
  - No, unclear, or unauthorized -> do not recommend a cloud routine; route to a local **loop** or a one-time mode.

After locality is settled, ask: **"What cadence - hourly, daily, or on some trigger?"** Record the cadence; it goes in the final output.

### Step 3 - Verification (do not skip this - it is the most important question)

Ask: **"How will Claude know it's actually done, without you checking manually? A test suite, a visual/pixel diff, a rubric, something else? Describe the check without sharing secrets or private data."**

This is the step people skip, and skipping it is why unattended runs stall or drift. If the user says "I don't know," "I'll just check it looks right," or gives no concrete mechanism:

- **Do not finalize the prompt.** Stop and help them define a verification method before moving on. Ask follow-up questions: is there an existing test suite? A reference output to diff against? A checklist a human would use? If truly nothing exists, help them sketch a minimal one (even "run X and confirm no errors plus manually spot-check Y" is better than nothing) before proceeding to Step 4.

Describe checks as draft text only. Do not run commands, open files, or verify systems while using this skill.

### Step 4 - Guardrails

Ask: **"Anything that must not be touched or broken - categories of files or systems, style rules, budget or token limits, anything off-limits? Use generic labels rather than private paths, account identifiers, or confidential details."**

If the user says "nothing," accept that but note it explicitly in the final output as "no additional task guardrails specified." The data, privacy, action, cloud, and high-risk boundaries in this skill still apply and cannot be waived by that answer.

### Step 5 - Check for an existing prompt covering this

Ask: **"Is there already a prompt, CLAUDE.md entry, or skill covering this task? Please answer yes or no; if context is needed, paste only a sanitized excerpt. I will not inspect or modify the file."**

- **Yes** -> tell the user not to layer the new prompt on top of the old one. Recommend that the user manually remove or comment out the existing instruction first, run the task without it, and only add back what actually breaks. Include this as an explicit advisory in the final output. Do not inspect, delete, comment, or edit the instruction yourself.
- **No** -> proceed, nothing to flag.

## Output format

After the interview and the data and safety gate are complete, produce exactly one markdown block using the structure in `references/output-template.md`. Do not add extra commentary inside the block. The block must contain:

1. **The final prompt** - written as outcome + guardrails + verification method, in prose, never as a numbered procedure. Replace sensitive details with labeled placeholders and include only minimized information.
2. **Data handling** - state that the draft is private and conversation-only, identify any redactions or authorization limits, and record cloud-transfer consent when relevant.
3. **Execution mode recommendation** - single agent / dynamic workflow / loop / routine - with a one-line reason tied back to the user's Step 2 answers. Never recommend an unattended mode for consequential high-risk decisions.
4. **Invocation snippet** - see `references/output-template.md` for the exact phrasing per mode.
5. **Human review requirement** - include when the task touches a high-risk domain.
6. **Ablation reminder** (only if Step 5 was "yes") - advisory instructions for the user to remove the old prompt/CLAUDE.md entry first.

## Worked example

The user opens with "I want our changelog to stop going stale."

**Step 1** - they answer "well, first read the commits, then group them, then write the entries." That's a procedure, so push back and ask for the end state. They restate: "CHANGELOG.md always has an accurate Unreleased section covering every merged PR since the last tag." That's outcome-shaped - proceed.

**Step 2** - recurring. They are considering cloud execution. Explain the cloud transfer boundary and ask for explicit consent after they remove private repository details. If they consent, a daily **routine** may be recommended; if they decline, recommend a local **loop**.

**Step 3** - they start with "I'll just read it and see if it looks right." Not a mechanism, so don't finalize. Follow up until it lands somewhere concrete: the draft should require comparing the identifiers in the Unreleased section against an authorized merged-change listing and confirming every entry appears exactly once. This skill describes that verification; it does not query the repository or account.

**Step 4** - guardrails: never edit released sections above `## [Unreleased]`, never touch version tags.

**Step 5** - yes, `CLAUDE.md` already has a "keep the changelog updated" line, so the output must advise the user to remove that line first rather than stacking the new prompt on top of it. This skill does not open or edit `CLAUDE.md`.

The final prompt is then written as prose - the outcome, the two guardrails, and the verification check - followed by data handling, the consent-appropriate execution recommendation, cadence, and the ablation note.

## Common failure modes

**The user answers Step 1 with a procedure.** Most people will. Don't accept it and don't quietly translate it yourself - ask them to restate it as an end state, because their own restatement is usually where they discover the outcome they actually want. Only proceed once the answer describes a result.

**Sensitive input appears.** Stop the interview, do not repeat the value, and ask for a redacted placeholder. If it is a credential, tell the user to revoke or rotate it through the appropriate service. Resume only with the minimized replacement.

**The user has no verification method.** This is the most common way the whole interview gets wasted. "I'll check it looks right" is not a mechanism, and a prompt built on it will drift on the first unattended run. Treat Step 3 as a hard gate: keep asking until there is something checkable, even if it is as modest as "the future runner executes the test suite and confirms no new failures, then a human spot-checks the three newest entries." This skill itself does not run the check.

**The final prompt drifts back into numbered steps.** Watch for this while drafting - it happens especially after a user has described a procedure in Step 1. If the draft has turned into an ordered list of instructions, rewrite it as outcome + guardrails + verification before showing it.

**Cloud is suggested without consent.** Explain the transfer boundary and ask one explicit consent question. A no, unclear answer, or lack of transfer authority routes to local execution; do not hide cloud transfer inside a generic routine recommendation.

**High-risk decisions become unattended.** Keep the prompt informational or organizational, require a qualified or authorized human review, and use a one-time reviewable mode. Do not route consequential decisions to a loop or routine.

## Guardrails for this skill itself

- Complete the data and safety gate before collecting task details or finalizing a prompt.
- Ask one question at a time and wait for the answer.
- Treat Step 3 as a hard gate; a prompt without concrete verification is incomplete.
- Write the final prompt as prose: outcome + task guardrails + verification, not a numbered procedure.
- Keep all input and output inside the current conversation as minimized text. Use no files, tools, accounts, network, external services, memory, or persistence.
- Produce a draft only. Perform no setup or external action even when the user asks to "just set it up."
- Recommend cloud only after disclosure, minimization, authorization, and explicit consent; otherwise choose local execution.
- Keep consequential high-risk decisions under qualified or authorized human review and out of unattended modes.
