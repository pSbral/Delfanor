# Skill: record-decision

**When:** A structural choice is closed (rules, services, product boundaries, tooling) and must not reopen casually.

## Steps

1. Confirm the decision is actually closed by the PM (use `clarify-with-pm` if options are still open).
2. Copy `documentation/decisions/_template.md` → `documentation/decisions/NNNN-slug.md` (next free number).
3. Fill: Status, Context, Options considered, Decision, Consequences, Supersedes (if any).
4. Keep it short; one decision per file.
5. Update `documentation/decisions/README.md` inventory.
6. If decision changes canonical rules/systems, update those docs **or** mark follow-up task — do not leave contradictions.
7. Close related `GAPS.md` rows or add follow-ups.

## Do not

- Use decisions as a changelog of every micro-edit.
- Reopen a closed decision without PM explicit reopen + new superseding record.
