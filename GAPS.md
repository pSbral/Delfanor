# GAPS — pending ledger (cross-session)

**Role:** Single durable list of open gaps, deferred work, and `INFORMAÇÃO AUSENTE` items the PM still needs to close. Survives model switches and machines.

**Parent:** [README.md](README.md)

**Maintainer:** skill [`skills/handoff/SKILL.md`](skills/handoff/SKILL.md) (required on session end) and any agent that discovers a new gap.

## How to use

- **Add** a row when something is unknown, deferred, or blocked (never invent a fill-in).
- **Update status** when progress happens: `open` | `in_progress` | `blocked` | `done`.
- **Move `done` rows** to the Archive section (keep short history) or delete if noise.
- **Handoff** must reconcile this file with folder-level Gaps sections and active task overviews.
- Domain notes in this file may be **PT-BR**; structural labels stay **English**.

## Open

| ID | Area | Description | Status | Next action | Related path |
| --- | --- | --- | --- | --- | --- |
| GAP-002 | rules | Conteúdo de regras canônicas ainda ausente (padrão um-arquivo-por-área já definido) | open | PM escolhe a 1ª área e fornece fatos; copiar `_template.md` | `documentation/rules/` |
| GAP-003 | systems | Sistemas do universo/mecânicas sem conteúdo | open | Preencher à medida que o design fechar | `documentation/systems/` |
| GAP-004 | services | Serviços compartilhados (ex. API Jogador) não inventariados | open | Onboard quando houver contrato real | `documentation/services/` |
| GAP-005 | glossary | Linguagem ubíqua / glossário vazio | open | Termos só com definição PM-aprovada | `documentation/ubiquitous-language/` |
| GAP-007 | incidents | Rotas de incidente/produção fora do MVP | open | Só quando houver operação real | Process Caller gap |
| GAP-008 | stack | Stack/CI/deploy não vivem neste repo; fatos por produto ausentes | open | Quando existir product entry | `documentation/products/` |
| GAP-009 | decisions | Decision log iniciado (0001); mais entradas quando houver escolhas | open | `record-decision` ao fechar novas escolhas | `documentation/decisions/` |

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
| When | 2026-08-07 — PT-BR contract + full push |
| Branch | `develop` |
| Active task | none |
| Summary | Feedback applied: EN agent machinery; PT-BR domain+chat; no ti; no PT-PT leakage; clarify-with-pm default; process pm-communication; DECISION-0001/0002; rules structure only; products/remotes empty. GAP-002…005,007…009 open. |
| Resume with | README → Process Caller → GAPS.md → clarify-with-pm next domain fill |

## Archive (done)

| ID | Area | Description | Closed |
| --- | --- | --- | --- |
| GAP-001 | products | PM confirmou 0 produtos (só repo de contexto); inventário vazio consciente | 2026-08-07 |
| GAP-006 | remotes | PM confirmou allowlist de remotes/paths externos vazia | 2026-08-07 |

## Gaps (meta)

- Do not invent domain fills for rows above.
- IDs are sequential (`GAP-NNN`); handoff assigns the next free ID.
