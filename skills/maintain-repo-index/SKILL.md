# Skill: maintain-repo-index

**When:** Any add/remove/rename of indexed folders or canonical markdown; adapter path changes; inventory drift.

## Steps

1. List intended tree vs disk.
2. For each indexed folder, ensure `README.md` has: Role, Parent, Inventory, Gaps, Children.
3. Update parent inventories to match real children (paths must exist).
4. Update root README inventory if top-level entries changed.
5. Ensure adapters only **point** to Process Caller / skills — no route table copy.
6. Run mental pass of index-auditor checks; fix broken links.
7. If new open unknowns appeared, add rows to root `GAPS.md`.
8. Commit on `develop` when work is complete (context repo policy).

## Do not

- Invent domain content while fixing indexes.
- Duplicate Process Caller routes into adapters.
