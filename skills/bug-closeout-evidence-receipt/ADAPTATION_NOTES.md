# Adaptation notes

This is a substantive safety and packaging adaptation of Pavel Putrenkov's MIT
licensed **Bug Receipt**.

Changes include:

- limits input to sanitized evidence intentionally supplied in the conversation;
- limits output to a private, reviewable Markdown or JSON-code-block draft;
- removes command execution, repository/file access, network lookup, monitoring,
  ticket, account, deploy, merge, approval, send, and publish capabilities;
- prevents supplied evidence from being represented as executed-now evidence;
- adds secret, personal-data, customer-data, and third-party minimization;
- adds high-risk human-authority routing and makes clear that a receipt is not
  approval, certification, incident closure, or deployment permission;
- makes the installed Skill self-contained and removes runtime dependence on the
  upstream JSON template, schema, and validator script.

The upstream author and fixed source remain credited. The Taku adapter/publisher
does not claim upstream authorship.
