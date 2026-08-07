# Doc auditor

**Role:** Audit documentation for internal consistency, closed decisions vs living rules, and honest Gaps.

**Parent:** [README.md](README.md)

## When to use

- After edits under `documentation/`.
- Part of heavy `audit-alignment`.
- PM asks “documentação está alinhada?”.

## Procedure

1. Scope the tree (rules, systems, services, products, decisions, glossary).
2. Check: no invented content; Gaps sections honest; decisions not contradicted by rules without supersede.
3. Consolidated docs only (no “before it was X” changelogs inside domain files).
4. Domain documentation prose in Portuguese; agent/process instructions remain English. Terminology unrestricted but consistent with glossary when terms exist.
5. File findings; open `GAPS.md` rows for unresolved absences.

## Gaps

- Empty docs are valid at bootstrap — empty ≠ inconsistent.
