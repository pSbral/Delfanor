# GAPS — pending ledger (cross-session)

**Role:** Single durable list of open gaps, deferred work, and `INFORMAÇÃO AUSENTE` items the PM still needs to close. Survives model switches and machines.

**Parent:** [README.md](README.md)

**Maintainer:** skill [`skills/handoff/SKILL.md`](skills/handoff/SKILL.md) (required on session end) and any agent that discovers a new gap.

## How to use

- **Add** a row when something is unknown, deferred, or blocked (never invent a fill-in).
- **Update status** when progress happens: `open` | `in_progress` | `blocked` | `done`.
- **Move `done` rows** to the Archive section (keep short history) or delete if noise.
- **Handoff** must reconcile this file with folder-level Gaps sections and active task overviews.
- Domain notes in this file may be **Portuguese**; structural labels stay **English**.

## Open

| ID | Area | Description | Status | Next action | Related path |
| --- | --- | --- | --- | --- | --- |
| GAP-001 | products | Inventário de produtos/repos do ecossistema vazio | open | PM lista nomes/remotes quando existirem | `documentation/products/` |
| GAP-002 | rules | Regras canônicas do RPG ainda não documentadas | open | PM / intake de regras compartilhadas | `documentation/rules/` |
| GAP-003 | systems | Sistemas do universo/mecânicas sem conteúdo | open | Preencher à medida que o design fechar | `documentation/systems/` |
| GAP-004 | services | Serviços compartilhados (ex. API Jogador) não inventariados | open | Onboard quando houver contrato real | `documentation/services/` |
| GAP-005 | glossary | Linguagem ubíqua / glossário vazio | open | Termos só com definição PM-aprovada | `documentation/ubiquitous-language/` |
| GAP-006 | remotes | Allowlist de paths/remotes de código externos ausente | open | Documentar quando repos existirem | `GAPS.md` / products |
| GAP-007 | incidents | Rotas de incidente/produção fora do MVP | open | Só quando houver operação real | Process Caller gap |
| GAP-008 | stack | Stack/CI/deploy não vivem neste repo; fatos por produto ausentes | open | Por product entry, não inventar | `documentation/products/` |
| GAP-009 | decisions | Decision Log ainda sem entradas | open | Usar `record-decision` ao fechar escolhas | `documentation/decisions/` |

## In progress

| ID | Area | Description | Status | Next action | Related path |
| --- | --- | --- | --- | --- | --- |
| — | — | Nenhuma | — | — | — |

## Blocked

| ID | Area | Description | Status | Blocked on | Related path |
| --- | --- | --- | --- | --- | --- |
| — | — | Nenhum | — | — | — |

## Last handoff

| Field | Value |
| --- | --- |
| When | 2026-08-07 — history reset + language policy |
| Branch | `develop` |
| Active task | none |
| Summary | Git history destroyed and rewritten as a single fresh commit so agents never load legacy product history. Language split locked: agents/skills/processes/adapters in English; domain docs in Portuguese; PM chat in standard Brazilian Portuguese. Domain still empty (GAP-001…009 open). |
| Resume with | Read README → Process Caller → this file → PM priority among GAP-001…009 (fill domain; do not invent) |

## Archive (done)

| ID | Area | Description | Closed |
| --- | --- | --- | --- |
| — | — | — | — |

## Gaps (meta)

- Do not invent domain fills for rows above.
- IDs are sequential (`GAP-NNN`); handoff assigns the next free ID.
