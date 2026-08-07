# Delfanor

**LLM: read this file entirely before acting.**

## Role

Source of truth and **agent context library** for the Delfanor ecosystem. Orchestrates shared documentation, processes, skills, and agents. **Does not host product application code.**

## What Delfanor is

Delfanor is an **authorial RPG ecosystem**: shared canonical rules across products, optional shared services (e.g. player query APIs), and multiple products (games, tools). Independent of where or how you play, a set of shared rules applies.

This repository is the **library agents use to stay aligned** with the PM (product owner) while building and maintaining that ecosystem.

## Standing preferences (do not ask to waive)

1. **Never invent.** Missing facts = `INFORMAÇÃO AUSENTE` in domain docs, or `INFORMATION ABSENT` in English structural files. Do not invent rules, services, products, APIs, glossary terms, or decisions.
2. **No credentials** in this repo (secrets, tokens, passwords, connection strings).
3. **Language (hard split — performance + PM UX)** — see [DECISION-0002](documentation/decisions/0002-language-split-ptbr.md) and process [`processes/pm-communication/`](processes/pm-communication/):
   - **English only** for agent machinery: `agents/`, `skills/`, `processes/`, `adapters/`, root instructional files (`README.md`, `AGENTS.md`, skill/agent bodies, route tables, index contracts). Models perform better on English instructions; keep that layer English.
   - **Brazilian Portuguese (PT-BR)** for **domain documentation** under `documentation/` and for domain notes in `GAPS.md` / task overviews — usable source of truth for the PM’s authorial RPG.
   - **Chat with the PM:** always **PT-BR**, clear and direct, address as **você**. **Forbidden defaults:** second-person **ti/te/tua** as address; European Portuguese (PT-PT) vocabulary/register (e.g. *ficheiro*, *factos*, *canónico*, *secção*, *registar*, *sítio* meaning “place/state”). Use natural BR wording (*arquivo*, *fatos*, *canônico*, *seção*, *registrar*, *pronto/no lugar*).
   - **Domain terminology is unrestricted** (English, Portuguese, or other languages as the domain requires). Do not translate established domain terms only for natural-language consistency.
4. **Pull, don't push.** Load the smallest context: this README → Process Caller → skills index → only the docs/skills needed for the classified route.
5. **Closed scope.** Do not reopen closed decisions or expand task scope without explicit PM reopening.
6. **PM clarification default (mandatory):** whenever you need to close a pending item, align requirements, prioritize, or resolve genuine ambiguity with the PM, use skill [`skills/clarify-with-pm/SKILL.md`](skills/clarify-with-pm/SKILL.md): **one topic per block**, **multiple-choice options with suggestions** (mark a recommended option when justified), and **always a free-text “Outra / resposta livre”** path. Prefer the runtime multi-choice UI when available; otherwise use the skill’s markdown format. Do not dump multi-topic open questionnaires.
7. **Raw demand intake does not auto-create tasks.** Use `validate-task` only when the PM asks (or after explicit validation path).
8. **Structural tree changes** always end with `maintain-repo-index`.
9. **Git policy:**
   - **This context repo:** edit + commit on `develop` is allowed.
   - **External product/code repos:** edit + commit **on a branch** (no force-push; protect main/master as applicable). Paths/remotes not listed yet = `INFORMATION ABSENT` / `INFORMAÇÃO AUSENTE` until inventory is filled.
10. **Session end / switch model:** run skill `handoff` so the next agent (any machine, any model) can resume from disk alone.
11. **Pending cross-session gaps** live in root [`GAPS.md`](GAPS.md). Keep it current; handoff must reconcile it.
12. **No legacy product inference.** This repo is a clean context library. Do not reconstruct products, rules, or stack from old git history, prior chats, or deleted trees unless the PM explicitly re-registers them.

## Bootstrap (every new session)

1. Read this `README.md` entirely.
2. Assume the **Process Caller** agent: [`agents/process-caller.md`](agents/process-caller.md).
3. Open [`skills/README.md`](skills/README.md); load **only** the skills required for the route.
4. If the PM says “continue”, “retomar”, or points at open work: read [`GAPS.md`](GAPS.md) and active task overviews under [`.activities/tasks/`](.activities/tasks/).
5. Classify the demand using the Process Caller route table (canonical there only — adapters must not duplicate it).
6. Pull minimal documentation for the touched area. Never inject the whole tree.

## Inventory (top level)

| Entry | When to open | Path |
| --- | --- | --- |
| Process Caller (dispatcher) | Every session after this README | [`agents/process-caller.md`](agents/process-caller.md) |
| Agents index | Need a specialist role | [`agents/README.md`](agents/README.md) |
| Skills index | After route classification | [`skills/README.md`](skills/README.md) |
| Processes | Prescriptive how-to for work | [`processes/README.md`](processes/README.md) |
| Documentation (reality) | Facts: rules, systems, services, products, decisions, glossary | [`documentation/README.md`](documentation/README.md) |
| Work memory (tasks) | Active / done tasks | [`.activities/README.md`](.activities/README.md) |
| Pending gaps ledger | Resume work; open unknowns | [`GAPS.md`](GAPS.md) |
| IDE adapters | Cursor / other thin entrypoints | [`adapters/README.md`](adapters/README.md) |
| AGENTS.md | Short IDE pointer file | [`AGENTS.md`](AGENTS.md) |

## Gaps

- Product/repo inventory and external remotes allowlist: **empty by PM confirmation** (2026-08-07); re-open when first product exists. See [`GAPS.md`](GAPS.md).
- Canonical rules, systems, services, glossary, and decisions still empty until the PM fills them.
- No production/incident routes in MVP.
- No stack/CI/deploy facts until product entries exist (code lives elsewhere).

## Children

- [`agents/`](agents/)
- [`skills/`](skills/)
- [`processes/`](processes/)
- [`documentation/`](documentation/)
- [`.activities/`](.activities/)
- [`adapters/`](adapters/)
- [`GAPS.md`](GAPS.md)
- [`AGENTS.md`](AGENTS.md)

## Index contract (all indexed folders)

Every indexed folder `README.md` after the title:

1. **Role** — one sentence  
2. **Parent** — link to the index above  
3. **Inventory** — table `Entry | When to open | Path`  
4. **Gaps** — explicit incompleteness / do not invent  
5. **Children** — direct children only; **do not** copy the Process Caller route table  

## Acceptance smoke (new chat)

- [ ] Agent reads README and assumes Process Caller  
- [ ] Named task pulls overview first  
- [ ] Raw paste does not create a task alone  
- [ ] Structural change ends with maintain-repo-index  
- [ ] Never invent / no credentials / closed scope present here  
- [ ] Handoff updates `GAPS.md` and leaves resume instructions on disk  
- [ ] PM clarification uses multi-choice + free-text (`clarify-with-pm`)  
