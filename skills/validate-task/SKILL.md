# Skill: validate-task

**When:** PM provides raw demand (paste, idea, bug note) and **explicitly** wants a structured task. Never run as silent side effect of paste alone.

## Steps

1. Restate goal, in-scope, out-of-scope, non-goals.
2. List unknowns as `INFORMAÇÃO AUSENTE` — do not invent.
3. If blocked on PM input, use skill `clarify-with-pm` (multi-choice + free-text; one topic per block).
4. On PM confirmation, create `.activities/tasks/<task-id>/` from `_template`.
5. Fill `overview.md` (English structure labels OK; domain narrative in **PT-BR** as needed).
6. Link related documentation paths if they exist; otherwise note gaps.
7. Update `.activities/tasks/README.md` inventory.
8. Add/update `GAPS.md` if the task depends on open gaps.
9. Do **not** start implementation until overview is accepted (unless PM says implement now).

## Task id convention

- Prefer `YYYYMMDD-short-slug` or `TASK-NNN` if a counter is introduced later.
- One folder per task.

## Do not

- Auto-create from unvalidated paste.
- Put secrets in overview.
