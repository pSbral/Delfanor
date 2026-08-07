# Skill: audit-alignment

**When:** PM requests full alignment audit; heavy review route; pre-release of context quality.

## Axes (run all that apply to scope)

| Axis | Agent | Focus |
| --- | --- | --- |
| Code | `agents/code-reviewer.md` | External repo diffs vs task + known docs |
| Documentation | `agents/doc-auditor.md` | Internal doc consistency, honest gaps, **rules area template + cross-ref graph** |
| Language | `agents/language-auditor.md` | Glossary vs usage + PT-BR locale / no ti / no PT-PT leakage |
| Index | `agents/index-auditor.md` | Index contract and graph (incl. rules inventory paths) |

## Steps

1. Agree scope with PM (paths, repos, “whole context repo”) via `clarify-with-pm` if scope is ambiguous.
2. Run axes in order: index → doc → language → code (skip code if no repo).
3. Produce a single findings list: blockers / majors / minors.
4. Open or update `GAPS.md` rows for unresolved items.
5. Do not invent missing domain content to “complete” the audit.
6. For follow-up prioritization of findings with the PM, use `clarify-with-pm`.

## Do not

- Fail the ecosystem for empty bootstrap docs — empty + honest Gaps is healthy.
