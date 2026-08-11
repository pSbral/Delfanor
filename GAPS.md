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
| GAP-004 | services | Serviços compartilhados (ex. API Jogador) não inventariados | open | Onboard só com contrato real; intenção em rascunho (GAP-010) | `documentation/services/` |
| GAP-005 | glossary | Linguagem ubíqua / glossário vazio | open | Termos só com definição PM-aprovada | `documentation/ubiquitous-language/` |
| GAP-007 | incidents | Rotas de incidente/produção fora do MVP | open | Só quando houver operação real | Process Caller gap |
| GAP-008 | stack | Stack/CI/deploy não vivem neste repo; fatos por produto ausentes | open | Quando existir product entry | `documentation/products/` |
| GAP-009 | decisions | Decision log iniciado (0001); mais entradas quando houver escolhas | open | `record-decision` ao fechar novas escolhas | `documentation/decisions/` |

## In progress

| ID | Area | Description | Status | Next action | Related path |
| --- | --- | --- | --- | --- | --- |
| GAP-010 | rascunhos | Visão de sessões RPG, portais mestre/jogador e API de dados do jogador — rascunho não canônico; PM pausou após visão parcial do `delfanor-portal-player` | in_progress | Retomar checklist `INFORMAÇÃO AUSENTE` no rascunho via `clarify-with-pm` (um tópico). Não onboard de produto; não promover a rules/glossary sem o PM | `documentation/rascunhos/visao-sessoes-portais-api-jogador.md` |

## Blocked

| ID | Area | Description | Status | Blocked on | Related path |
| --- | --- | --- | --- | --- | --- |
| — | — | Nenhum | — | — | — |

## Last handoff

| Field | Value |
| --- | --- |
| When | 2026-08-11 — audit-alignment + persist rascunho na `develop` |
| Branch | `develop` |
| Active task | none (intake não virou tarefa) |
| Summary | Auditoria índice/doc/idioma no repo de contexto (sem eixo de código). Correções: `documentation/` deixa explícito que rascunhos não são realidade; handoff sem “RGB”. Rascunho GAP-010 permanece não canônico. Visão parcial de `delfanor-portal-player` (chat, rolagem, ficha ≠ aparência, criação nome/raça/vermelho-azul-verde/origem, inventário alterável, nível na ficha). Produtos/serviços/rules não onboarded. |
| Resume with | README → Process Caller → `GAPS.md` (GAP-010) → `documentation/rascunhos/visao-sessoes-portais-api-jogador.md` (INFORMAÇÃO AUSENTE) → `clarify-with-pm` um tópico. Não inventar. |

## Archive (done)

| ID | Area | Description | Closed |
| --- | --- | --- | --- |
| GAP-001 | products | PM confirmou 0 produtos (só repo de contexto); inventário vazio consciente | 2026-08-07 |
| GAP-006 | remotes | PM confirmou allowlist de remotes/paths externos vazia | 2026-08-07 |

## Gaps (meta)

- Do not invent domain fills for rows above.
- IDs are sequential (`GAP-NNN`); handoff assigns the next free ID.
