# DECISION-0002: Idioma — máquina em inglês; domínio e chat em PT-BR

| Field | Value |
| --- | --- |
| Status | Accepted |
| Date | 2026-08-07 |
| Deciders | PM |

## Context

Modelos performam melhor com instruções em inglês. O PM é falante de português brasileiro e o RPG é projeto autorial; documentação de domínio e conversa devem ser usáveis por ele. Feedback explícito: não usar registro informal com **ti** e não escrever em português europeu — preferir PT-BR natural (**você**, arquivo, fatos, canônico, seção, registrar).

## Options considered

1. **Tudo em português** — pior para skills/agents; risco de mistura PT-BR/PT-PT.
2. **Tudo em inglês** — pior UX do PM no domínio do RPG.
3. **Split** — inglês na máquina de agentes; PT-BR no domínio e no chat.

## Decision

- **English only:** `agents/`, `skills/`, `processes/`, `adapters/`, root instructional contracts.
- **Brazilian Portuguese (PT-BR):** domain docs under `documentation/`, domain notes in `GAPS.md`/tasks, and **all chat with the PM**.
- **Terminology** of the game world remains unrestricted (any language as the domain requires).
- Process detail: `processes/pm-communication/`. Clarification UX: `skills/clarify-with-pm`.

## Consequences

- Agents must not invent domain content to “sound complete”.
- Language auditor flags PT-PT leakage in PM-facing/domain Portuguese.
- New skills stay English; user-visible question labels in clarify blocks stay PT-BR.

## Supersedes

None
