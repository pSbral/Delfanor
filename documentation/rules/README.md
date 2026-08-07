# Rules (canonical RPG)

**Role:** Shared rules that apply regardless of product or play medium.

**Language:** Domain prose in **Portuguese**; structural labels on this index may stay English. Terminology unrestricted.

**Parent:** [../README.md](../README.md)

## Inventory

| Entry | When to open | Path |
| --- | --- | --- |
| Area template | Creating a new rules area file | [_template.md](_template.md) |

## Organization pattern (binding)

Confirmed with the PM (see [DECISION-0001](../decisions/0001-rules-one-file-per-area.md)):

1. **One markdown file per rules area** under `documentation/rules/` (not a single monolith).
2. Areas **may cross-reference** each other via the **Referências a outras regras** table in each file.
3. Every area file is created from [`_template.md`](_template.md) and listed in this inventory.
4. Do **not** invent rule text. Use `INFORMAÇÃO AUSENTE` until the PM provides content.
5. After add/remove/rename of area files → update this inventory + skill `maintain-repo-index` if the tree contract drifts.
6. Consistency / link graph → **doc-auditor** (rules cross-ref pass) as part of `audit-alignment` or after bulk rule edits.

### Suggested file naming

`documentation/rules/<slug-area>.md`  
Examples of slugs (placeholders only — **not** registered areas): `combate`, `personagem`, `progressao`. Create a file only when the PM opens that area.

### Indexing checklist (agents)

When touching rules:

- [ ] New file from `_template.md`
- [ ] Row added/updated in Inventory above
- [ ] Children list matches real area files (not the template alone if others exist)
- [ ] Outbound links in Referências resolve or are marked `INFORMAÇÃO AUSENTE`
- [ ] Inbound: if area B cites A, A’s scope still honest
- [ ] Glossary candidates listed; no silent new terms (GAP-005 / `apply-ubiquitous-language`)
- [ ] Run **doc-auditor** rules pass after multi-file edits

## Gaps

- **INFORMAÇÃO AUSENTE:** nenhuma área canónica preenchida ainda (GAP-002).
- Estrutura e padrão existem; conteúdo de regras ainda não.
- Do not invent rules or area files “to look complete”.

## Children

- [_template.md](_template.md)
