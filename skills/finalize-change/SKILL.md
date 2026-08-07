# Skill: finalize-change

**When:** Implementation or substantial doc change is ready to close (pre-merge / pre-done).

## Steps

1. Re-read task overview scope in/out — reject silent scope creep.
2. **Context repo:** ensure indexes updated if structure changed (`maintain-repo-index`).
3. **External code repo:** on feature branch; commit with clear message; no force-push; no secrets.
4. Run appropriate review: `code-reviewer` and/or `doc-auditor` / language / index as needed.
5. Update task overview status; move to `.activities/done/` when PM accepts complete.
6. Reconcile `GAPS.md` (close or open rows).
7. Offer `handoff` if the session ends here.

## Quality checklist (generic — no stack lock-in)

- [ ] Scope respected  
- [ ] No invented domain facts  
- [ ] No credentials committed  
- [ ] Docs/indexes match reality  
- [ ] Tests/validation: as defined by the **product** repo (if unknown = `INFORMAÇÃO AUSENTE`, ask PM)  

## Do not

- Bind this skill to a specific language, CVE tool, or package manager until a product declares it.
