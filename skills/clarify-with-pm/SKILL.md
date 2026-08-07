# Skill: clarify-with-pm

**Aliases / triggers:** pending gaps, requirements alignment, “preciso esclarecer”, blocked on PM choice, continuous requirement sync, any genuine ambiguity that needs a PM decision.

**When (default):** **Always** when the agent needs the PM to close an unknown, pick among options, prioritize work, confirm scope, or align requirements. This is the **default** clarification UX — not optional polish.

## Goal

Keep alignment cheap and explicit: the PM chooses from **suggested options** or types a **personal free-text answer**, without open-ended interrogation dumps.

## Rules

1. **One topic per question block** (not one word — one decision surface). Do not stack unrelated topics in one block.
2. **Multiple-choice by default.** Offer **2–5 concrete options** when possible.
3. Mark a **recommended** option when the agent has a justified preference (one sentence why).
4. **Always** include a free-text path: label it clearly, e.g. **Outra / resposta livre:** (or runtime “Other”).
5. Options may be multi-select when several answers can be true at once (say so explicitly).
6. **PM-facing text is PT-BR only** (see `processes/pm-communication/`): **você**, natural Brazilian wording; never default **ti**; no PT-PT chat vocabulary (*ficheiro*, *sítio*, *factos*, *canónico*, *secção*, *registar*). Skill body stays English.
7. Do **not** invent domain facts inside options. If an option is a hypothesis, label it as suggestion, not as established truth.
8. After the PM answers: apply the choice, update docs/task/`GAPS.md` as needed, then continue. Do not re-ask the same topic unless the answer was incomplete.

## Format (markdown fallback — any runtime)

Use when the IDE has no dedicated multi-choice widget. Labels and options in **PT-BR**:

```text
### <Título do tópico — uma decisão>

Contexto em 1–3 frases (só fatos ou INFORMAÇÃO AUSENTE).

- **A)** <opção> — <implicação curta>
- **B)** <opção> — <implicação curta>  ← recomendado: <motivo em uma frase>
- **C)** <opção> — <implicação curta>
- **Outra / resposta livre:** (escreva o que preferir)

Responda com a letra, várias letras se multi-seleção, e/ou texto livre.
```

## Format (runtime multi-choice UI)

When the environment provides a multi-choice / multi-select control (e.g. structured question tool):

1. One question object per topic.
2. Options = suggestions; put the recommended option first when the UI supports ordering.
3. Ensure free-text / “Other” is available (if the tool always adds it, do not omit options assuming free text alone is enough).
4. Prefer multi-select only when simultaneous picks are valid.

## When **not** to use

- Pure execution of already closed PM instructions (no new ambiguity).
- Yes/no that is truly binary and already phrased by the PM as a single closed order — still prefer A/B if residual ambiguity remains.
- Emergencies where the PM already gave an explicit one-line answer in the same turn.

## Integration

| Caller | How |
| --- | --- |
| Process Caller | Standing rule: any PM clarification → this skill’s format |
| `validate-task` | Clarifying unknowns before task creation |
| Gap fill / onboard | Prioritization and fact intake |
| `record-decision` | Options considered may start as clarify blocks |
| `handoff` | Leave next clarify topic listed if still open |

## Do not

- Dump a questionnaire of many topics at once without sequencing.
- Offer only free-text with zero suggestions when options are knowable.
- Use **ti** as address, PT-PT wording, or invent domain fills to pad options.
- Write chat like European Portuguese or with odd calques the PM already rejected (e.g. *sítio* for “ready/in place”).
