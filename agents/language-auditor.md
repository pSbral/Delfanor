# Language auditor

**Role:** Enforce ubiquitous language consistency **and** PT-BR quality for PM-facing/domain Portuguese (no PT-PT leakage, no **ti** address).

**Parent:** [README.md](README.md)

## When to use

- After glossary or domain-heavy edits.
- After edits that change how agents should speak to the PM.
- Part of `audit-alignment`.
- Skill `apply-ubiquitous-language` may invoke this role.
- Process `processes/pm-communication/` is the chat contract.

## Procedure

### A. Ubiquitous language

1. Load `documentation/ubiquitous-language/` (if empty, report GAP-005 only).
2. Scan touched docs/tasks for conflicting synonyms of defined terms.
3. Do **not** invent glossary entries; propose candidates only with PM approval (`clarify-with-pm` if needed).
4. Domain terms are not force-translated; flag inconsistent mixed names for the same concept without Decision/glossary support.

### B. Locale and register (PT-BR)

Binding: [DECISION-0002](../documentation/decisions/0002-language-split-ptbr.md), root README language split, `processes/pm-communication/`.

1. **Agent machinery** (`agents/`, `skills/`, `processes/`, adapters) must remain **English** (except short quoted PM-facing examples).
2. **Domain docs** and **GAPS domain notes** should be **PT-BR**. Flag clear PT-PT leakage (rewrite to BR forms: arquivo, fatos, canônico, seção, registrar; avoid European “place/state” calques the PM rejected).
3. **Chat samples / clarify templates** must use **você**, never default **ti/te/tua** as address.
4. Do not fail the audit for English structural labels in bilingual index files (Role/Parent/Inventory).
5. Mentions of forbidden forms **inside** DECISION/process docs that *forbid* them are not leaks if the surrounding prose is PT-BR and instructional.

### C. Report

- Findings: blockers / majors / minors.
- Open or update `GAPS.md` only for real unresolved absences (not for style nits fixed in the same pass).

## Gaps

- Glossary is empty at baseline (GAP-005).
- Locale rules are active even when the glossary is empty.
