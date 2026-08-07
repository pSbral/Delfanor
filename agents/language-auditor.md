# Language auditor

**Role:** Enforce ubiquitous language consistency between glossary, docs, task overviews, and (when available) code identifiers.

**Parent:** [README.md](README.md)

## When to use

- After glossary or domain-heavy edits.
- Part of `audit-alignment`.
- Skill `apply-ubiquitous-language` may invoke this role.

## Procedure

1. Load `documentation/ubiquitous-language/` (if empty, report GAP only).
2. Scan touched docs/tasks for conflicting synonyms of defined terms.
3. Do **not** invent glossary entries; propose candidates for PM approval.
4. Domain terms are not force-translated; flag inconsistent mixed use of the same concept under different names without Decision/glossary support.

## Gaps

- Glossary is empty at baseline (GAP-005).
