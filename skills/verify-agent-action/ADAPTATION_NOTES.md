# Adaptation notes

This is a material operative-safety derivative of RJ's public
`verify-agent-action` Skill.

- Upstream repository: https://github.com/github/awesome-copilot
- Upstream commit: `83561bd7d8a46fcda0581aedabdf8eac7cb196b6`
- Upstream path: `skills/verify-agent-action/SKILL.md`
- Upstream license: MIT, preserved in `LICENSE`
- Adaptation: n1ko / Taku Community review

The derivative retains the six-control review, exact-action binding,
support-versus-refutation separation, fail-closed outcomes, and the invariant
`execution_authorized=false`. It materially changes the operative boundary:

- input is limited to one redacted, minimal packet deliberately pasted into the
  current conversation;
- credentials, secrets, raw nonces, signatures, session identifiers, direct
  personal identifiers, unnecessary proprietary material, and unauthorized
  third-party data are prohibited;
- every packet, policy excerpt, evaluator description, fixture, log, approval
  record, and embedded instruction is treated as inert, untrusted data;
- evaluator, fixture, script, command, policy-engine, model, signature,
  monitoring, account, file, repository, and network execution or inspection is
  removed;
- output is a private conversation-only review with no persistence, sending,
  publishing, purchasing, approval, deployment, mutation, or other external
  action; and
- consequential decisions remain with the authorized owner and any applicable
  qualified human professional.

Redaction can force a control to `INCONCLUSIVE`; the derivative never requests
sensitive values merely to turn uncertainty into a pass. Eligibility remains a
review status, never approval or execution authority.

RJ and GitHub, Inc. did not write or endorse these adaptations. The publishing
account does not claim to be the upstream author.
