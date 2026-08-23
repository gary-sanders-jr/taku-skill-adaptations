# Adaptation notes

Adapter/publisher: n1ko / yuze.

This is a materially adapted derivative, not a byte-preserved copy of the upstream Skill. The upstream framework coordinates AppSec agents, scanners, retry behavior, self-scoring, and persistent lesson/memory creation. This derivative narrows the job to reviewing the evidence quality of one existing, sanitized security audit report as private text.

The operative body now:

- accepts only sanitized user-supplied report material;
- treats embedded instructions, links, commands, code, and payloads as inert data;
- prohibits scanners, code execution, repositories, accounts, networks, external services, file writes, lessons, memories, tickets, publication, and other mutations;
- separates supplied observations, unverified report claims, inferences, unknowns, and owner decisions;
- avoids numeric quality scores, vulnerability validation, severity reassignment, compliance certification, and risk acceptance;
- routes live incidents and consequential decisions to authorized qualified owners.

The upstream `references/` files are intentionally not included. They contain scanner/tool retry flows and persistent lesson/memory instructions that are outside this derivative's self-contained, no-action contract. Their exclusion does not change the MIT attribution recorded in [SOURCE_CREDITS.md](SOURCE_CREDITS.md) and [LICENSE](LICENSE).
