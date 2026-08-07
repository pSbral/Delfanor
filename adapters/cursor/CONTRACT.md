# Cursor adapter contract

**Role:** Binding thin contract for agents running inside Cursor (including Composer).

**Parent:** [../README.md](../README.md)

## Must

1. Read root [`README.md`](../../README.md) entirely at session start.  
2. Assume Process Caller: [`agents/process-caller.md`](../../agents/process-caller.md) — **route table lives only there**.  
3. Open [`skills/README.md`](../../skills/README.md); load only required skills.  
4. For resume / open work: [`GAPS.md`](../../GAPS.md).  
5. On session end or PM `/handoff`: [`skills/handoff/SKILL.md`](../../skills/handoff/SKILL.md).  
6. Never invent domain facts; no credentials.  
7. Git: commit OK on this context repo (`develop`); external code → branch + commit; no force-push to product defaults.  
8. Structural edits → `maintain-repo-index`.  
9. Language: agent machinery **English**; domain docs + PM chat **PT-BR** (`você`; no **ti**; no PT-PT chat vocabulary). See `processes/pm-communication/` and DECISION-0002.  
10. PM clarification / requirements alignment → skill `clarify-with-pm` (multi-choice suggestions + free-text; one topic per block). Use runtime multi-choice UI when available.  

## Must not

- Copy or fork the Process Caller route table into rules/AGENTS fragments.  
- Auto-create tasks from raw paste.  
- Infer products/rules from deleted trees, old remotes, or non-canonical history.
- Dump open multi-topic questionnaires when structured multi-choice is possible.
- Address the PM as **ti** or write PM-facing text in European Portuguese.

## Optional Cursor wiring

If you add `.cursor/rules` later, each rule should be a **pointer** (links above), not a second manual.
