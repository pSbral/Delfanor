# Skill: handoff

**Aliases / triggers:** `/handoff`, “vou parar”, “prepara o handoff”, “troca de modelo”, “continua noutro PC”, session interrupt outside a clean task close.

**When:** Always before ending a session that changed state **or** when the PM will resume later with another model/agent. Normal “task fully done + finalize-change” still benefits from a short handoff if anything remains open.

## Goal

The **next agent with zero chat memory** must resume from **disk only**: README → Process Caller → `GAPS.md` → active task overview.

## Steps (mandatory order)

### 1. Snapshot working state

- `git status` / branch name on this context repo (and external repos touched).
- Uncommitted work: finish or explicitly list as WIP in `GAPS.md` / task overview — do not leave silent dirty state without documentation.
- Active task id (if any).

### 2. Update the active task (if any)

In `.activities/tasks/<id>/overview.md`:

- Status, last route used  
- Done this session  
- Remaining work (ordered)  
- Blockers / `INFORMAÇÃO AUSENTE`  
- Pointers to files/repos touched  

If task is complete: run `finalize-change` path to move to `done/` (or note PM still needs to accept).

### 3. Reconcile root `GAPS.md` (critical)

- Add new gaps with next `GAP-NNN` id.  
- Update status: `open` | `in_progress` | `blocked` | `done`.  
- Move finished items to Archive.  
- Refresh **Last handoff** section:

| Field | Content |
| --- | --- |
| When | ISO date + short time or session label |
| Branch | e.g. `develop` |
| Active task | id or `none` |
| Summary | 2–5 sentences: what changed, what is true now |
| Resume with | Exact first files/routes for the next agent |

### 4. Indexes

- If structure changed: `maintain-repo-index`.  
- Ensure folder Gaps sections do not contradict `GAPS.md` (ledger is cross-session source; folder Gaps stay short).

### 5. Commit (context repo)

- Commit durable handoff artifacts on `develop` when policy allows (edit+commit OK here).  
- Message example: `chore(handoff): snapshot session state`.  
- Do not force-push.  
- External repos: commit on their feature branches if work is complete enough; otherwise document WIP in GAPS/overview.

### 6. Reply to PM (short)

- What was persisted  
- Active task + top open GAPs  
- One-line “next agent should…”  

## Minimal template for Last handoff summary

```text
Session: <goal>
Changed: <paths>
Open: GAP-…, task …
Next: Read GAPS.md → overview → <route>
```

## Do not

- Rely on chat history as source of truth.  
- Invent fills for open gaps “to look complete”.  
- Skip `GAPS.md` because “nothing big happened” if any WIP or unknown remains.  
- Delete open GAP rows without PM intent.
