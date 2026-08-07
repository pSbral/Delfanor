# Process: PM communication

**Role:** How agents speak with and clarify requirements with the product owner (PM).

**Language:** This process file is **English**. Chat output to the PM is **Brazilian Portuguese (PT-BR)**.

**Parent:** [../README.md](../README.md)

## Inventory

| Entry | When to open | Path |
| --- | --- | --- |
| clarify-with-pm skill | Multi-choice alignment UX | [../../skills/clarify-with-pm/SKILL.md](../../skills/clarify-with-pm/SKILL.md) |

## When to use

- Every reply to the PM.
- Any pending item, requirements alignment, or ambiguity → also load `clarify-with-pm`.

## Rules (binding)

1. **Locale:** Brazilian Portuguese (**PT-BR**), not European Portuguese (PT-PT).
2. **Register:** Clear, direct, professional-casual. Address the PM as **você**. Never use second-person **ti** / **tua** / **te** as the default address form.
3. **No PT-PT filler or vocabulary** in chat or domain prose written for the PM. Prefer BR forms, for example:
   - Use **arquivo** not *ficheiro*
   - Use **fatos** not *factos*
   - Use **canônico/canônica** not *canónico*
   - Use **seção** not *secção*
   - Use **registrar/registrado** not *registar/registado*
   - Do **not** use *sítio* to mean “place/state of things” (sounds foreign/odd in BR chat); say **pronto**, **no lugar**, **ok**, **fechado**
4. **Do not invent** domain facts. Mark gaps as `INFORMAÇÃO AUSENTE`.
5. **Clarification default:** skill `clarify-with-pm` — one topic per block, suggested options, recommended when justified, always free-text “Outra / resposta livre”.
6. Agent machinery (this file, skills, agents) stays **English**; only **user-facing chat** and **domain docs** are PT-BR.

## Steps (clarification)

1. State minimal factual context (or `INFORMAÇÃO AUSENTE`).
2. Ask via `clarify-with-pm` format (runtime multi-choice if available).
3. Apply the PM answer to docs/tasks/`GAPS.md`.
4. Continue work; do not re-open closed answers without cause.

## Related skills / agents

- `skills/clarify-with-pm`
- `agents/process-caller` (standing rules)
- `agents/language-auditor` (PT-BR + glossary pass)

## Gaps

- None for the process itself; domain content still incomplete (see root `GAPS.md`).

## Children

None (leaf process).
