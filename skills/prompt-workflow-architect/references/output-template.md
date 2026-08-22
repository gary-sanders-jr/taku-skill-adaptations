# Output Template

Fill this exact structure once the interview and data and safety gate in `SKILL.md` are complete. Replace the bracketed text. Do not include brackets or instructions in the final output shown to the user.

---

## Template

```markdown
### Prompt

[Write the minimized outcome the task should reach, in prose. One or two paragraphs maximum. State what done looks like. Do not number this as steps and do not reproduce sensitive details.]

**Guardrails:** [Task-specific limits. If the user specified none, write "No additional task guardrails specified." The Skill's privacy, action, cloud, and high-risk boundaries still apply.]

**Verification:** [Exactly how a future authorized runner should confirm correctness. This must be concrete, never "check that it looks right." This Skill does not run the check.]

### Data handling

**Input:** [State that only minimized, sanitized, authorized text was used. Name placeholders or omitted categories without reproducing values.]

**Output:** Private, reviewable draft in this conversation only. Nothing was read, written, saved, sent, published, scheduled, or configured.

**Cloud transfer:** [Not applicable | Declined; local mode selected | Explicitly consented for the minimized task after disclosure.]

### Execution mode: [Single agent | Dynamic workflow | Loop | Routine]

**Why:** [Tie the recommendation to scope, recurrence, locality, cloud consent, and any high-risk boundary.]

### Invocation

[Use the matching block below.]

[When the task is high-risk, append the Human review block below.]
```

---

## Invocation snippets by mode

**Single agent** (small, one-time):

```text
Paste the Prompt, Guardrails, and Verification text above into a new Claude Code conversation after reviewing it. No special invocation is needed.
```

**Dynamic workflow** (large, one-time, multi-stage):

```text
After reviewing the Prompt, Guardrails, and Verification text above, paste it into Claude Code and append: "Use a workflow."
```

**Loop** (recurring, must stay local):

```text
Cadence: [for example, every day at 9am or on an approved local trigger]
Runs: locally (requires the machine to stay on)

[Paste the Prompt, Guardrails, and Verification text above as the recurring instruction after reviewing it.]

NOTE: This is a draft. The user must set up any local loop themselves. This Skill did not read files, change configuration, or create or schedule the loop.
```

**Routine** (recurring, cloud transfer explicitly consented):

```text
Cadence: [for example, every day or every Monday]
Runs: in the cloud using only the minimized data the user explicitly authorized for transfer

[Paste the Prompt, Guardrails, and Verification text above as the recurring instruction after reviewing it.]

NOTE: This is a draft. The user must set up any cloud routine themselves and confirm the provider's current data controls. This Skill did not access an account, transfer data, change configuration, or create or schedule the routine.
```

## Human review block for high-risk domains

```markdown
### Human review required

This draft is informational or organizational only. A relevant qualified professional or authorized owner must review the source material, conclusions, and any proposed action. Do not use this prompt to make, communicate, or enforce consequential decisions unattended.
```

## If Step 5 was yes

Append this advisory after Invocation. The Skill does not perform these actions.

```markdown
### Before you use this

You said an existing prompt or instruction already covers this task. Review and manually disable that existing instruction before testing the new draft so the two do not stack. Restore only the parts you later confirm are necessary.
```
