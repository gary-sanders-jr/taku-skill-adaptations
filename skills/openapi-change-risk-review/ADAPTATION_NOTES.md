# Adaptation notes

The upstream `openapi-spec` Skill teaches specification creation, TypeScript client generation, Redocly linting, and preview tooling. That operative body is not safe for a least-privilege, text-review-only Taku Community package because it invokes commands and creates or changes files.

This Apache-2.0 derivative narrows the job to reviewing user-pasted, sanitized before-and-after OpenAPI excerpts. It preserves the upstream subject matter—OpenAPI contract design and compatibility—but replaces all file creation, generators, linters, previews, repository access, network access, and implementation actions with an evidence-labeled private text report. It adds explicit privacy, prompt-injection, uncertainty, rights, high-risk routing, and no-external-action boundaries.

Adapter and publisher: n1ko / yuze. Upstream contributors and Terminal Skills remain credited in `SOURCE_CREDITS.md`.

