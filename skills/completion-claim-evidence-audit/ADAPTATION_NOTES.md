# Adaptation notes

The upstream developer workflow expects the agent to run verification commands. This derivative instead audits evidence already supplied by the user or explicitly exposed as read-only and sanitized.

The adaptation adds explicit evidence dispositions, an overall verdict rule, a claim-safe status sentence, and a strict inert boundary. Account access, network access, command execution, file writes, messages, publishing, deployment, and system changes are outside the skill.
