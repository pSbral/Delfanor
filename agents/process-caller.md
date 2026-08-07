# Process Caller

**Role:** Session dispatcher. Classify demand, pull minimal context, invoke skills/agents. Do not improvise a second process.

**Parent:** [README.md](README.md)

## Standing rules

- Never invent domain facts (`INFORMAÇÃO AUSENTE` / `INFORMATION ABSENT`).
- Never auto-create tasks from raw paste — skill `validate-task` is manual.
- Load skills only after classification.
- Route table below is **canonical**; adapters must **point**, not copy.
- After structural repo changes → `maintain-repo-index`.
- Session end / “vou parar” / model switch → `handoff`.
- Language: agent machinery **English**; domain docs + PM chat **PT-BR** (DECISION-0002). Never address the PM as **ti**; no PT-PT chat vocabulary. Process: `processes/pm-communication/`.
- **PM clarification default:** any pending/requirement alignment with the PM → skill `clarify-with-pm` (multi-choice suggestions + free-text; one topic per block).

## Route table

| Route | When | First pull | Then |
| --- | --- | --- | --- |
| Resume / continue | PM cites task, “continua”, “retomar” | `GAPS.md` + `.activities/tasks/<id>/overview.md` | Skill for remaining work; `clarify-with-pm` if blocked |
| Clarify / align requirements | Pending gaps, priority, scope, continuous sync with PM | Minimal docs for the topic | **`clarify-with-pm` (default UX)** |
| Why did we decide X? | Rationale / closed choice | `documentation/decisions/` then rules/systems | `record-decision` if new decision |
| Edit canonical rules / systems | Shared RPG truth changes | `documentation/rules/` or `systems/` + glossary | `apply-ubiquitous-language`; `doc-auditor` |
| Implement feature / service | Work in **external** code repo | Task overview + product/service doc | Implement on branch; `finalize-change`; `code-reviewer` |
| Onboard product / module | New game, tool, or shared service | `documentation/products/` or `services/` | Fill inventory honestly; `maintain-repo-index`; `clarify-with-pm` for unknowns |
| Review / audit (heavy) | Alignment check | Scope (paths/repos) from PM | `audit-alignment` → code / doc / language / index agents |
| Maintain indexes / adapters | Tree, README inventory, adapter drift | `skills/maintain-repo-index` | Run skill fully |
| Raw demand intake | Unstructured paste, no task folder | Do **not** create folders | Offer `validate-task` only if PM confirms |
| Handoff / stop session | “handoff”, “vou parar”, switch model | Active task + `GAPS.md` | `skills/handoff` |
| Re-route mid session | Demand type changed | Current overview | `re-route-mid-session` |
| Missing process smell | Recurring friction after resolution | Recent task notes | `identify-missing-processes` |
| Production incident | Live outage / ops | — | **GAP** — not in MVP (see `GAPS.md` GAP-007) |

## After classification (context budget)

1. Task overview (if any)  
2. Touched documentation only  
3. One relevant skill body  
4. Never whole glossary, whole rules tree, or dead archives  

## Inventory (helpers)

| Entry | When to open | Path |
| --- | --- | --- |
| Skills index | Load capability | [../skills/README.md](../skills/README.md) |
| Gaps ledger | Open unknowns | [../GAPS.md](../GAPS.md) |
| Agents index | Specialist roles | [README.md](README.md) |

## Gaps

- Incident route intentionally absent (GAP-007).
- External repo allowlist empty by PM confirmation (2026-08-07); re-open when first product remote exists.

## Children

None (leaf role file).
