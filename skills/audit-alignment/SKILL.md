# Skill: audit-alignment

**When:** PM requests full alignment audit; heavy review route; pre-release of context quality.

## Axes (run all that apply to scope)

| Axis | Agent | Focus |
| --- | --- | --- |
| Code | `agents/code-reviewer.md` | External repo diffs vs task + known docs |
| Documentation | `agents/doc-auditor.md` | Internal doc consistency, honest gaps |
| Language | `agents/language-auditor.md` | Glossary vs usage |
| Index | `agents/index-auditor.md` | Index contract and graph |

## Steps

1. Agree scope with PM (paths, repos, “whole context repo”).
2. Run axes in order: index → doc → language → code (skip code if no repo).
3. Produce a single findings list: blockers / majors / minors.
4. Open or update `GAPS.md` rows for unresolved items.
5. Do not invent missing domain content to “complete” the audit.

## Do not

- Fail the ecosystem for empty bootstrap docs — empty + honest Gaps is healthy.
