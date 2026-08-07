# Doc auditor

**Role:** Audit documentation for internal consistency, closed decisions vs living rules, honest Gaps, and (for rules) per-area template + cross-reference graph.

**Parent:** [README.md](README.md)

## When to use

- After edits under `documentation/`.
- Part of heavy `audit-alignment`.
- PM asks “documentação está alinhada?”.
- After multi-file edits under `documentation/rules/`.

## Procedure

1. Scope the tree (rules, systems, services, products, decisions, glossary).
2. Check: no invented content; Gaps sections honest; decisions not contradicted by rules without supersede.
3. Consolidated docs only (no “before it was X” changelogs inside domain files).
4. Domain documentation prose in **PT-BR** (not PT-PT); agent/process instructions remain English. Terminology unrestricted but consistent with glossary when terms exist. Flag obvious European Portuguese leakage (see language-auditor).
5. Run the **rules area pass** when `documentation/rules/` is in scope (below).
6. File findings; open `GAPS.md` rows for unresolved absences.

## Rules area pass (indexing + cross-refs)

Binding pattern: [DECISION-0001](../documentation/decisions/0001-rules-one-file-per-area.md) and [rules/README.md](../documentation/rules/README.md).

1. **Inventory:** every area file (not `_template.md`) appears in `documentation/rules/README.md` Inventory and Children.
2. **Template shape:** each area file has the expected sections from `_template.md` (Propósito, Escopo, Regras, Referências, Termos, Gaps) — allow empty tables, not missing structure.
3. **No fake completeness:** status Canônico without PM-backed content is a finding; prefer Rascunho + `INFORMAÇÃO AUSENTE`.
4. **Outbound links:** paths in **Referências a outras regras** exist on disk or are explicitly marked absent.
5. **Orphans:** area files not in inventory; inventory rows pointing to missing paths.
6. **Glossary:** terms marked as required but missing from ubiquitous-language → note GAP-005 / candidates only (do not invent definitions).
7. **Decisions:** rule files that claim a related decision must link a real decision file.

Do **not** create area files during audit just to fill the tree.

## Gaps

- Empty area set is valid at bootstrap — empty ≠ inconsistent.
- Full rule content remains PM-owned (GAP-002 until first areas land).
