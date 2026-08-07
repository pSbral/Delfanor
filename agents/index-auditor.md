# Index auditor

**Role:** Verify the index graph: every indexed folder README has Role / Parent / Inventory / Gaps / Children; inventories match real children; adapters stay thin.

**Parent:** [README.md](README.md)

## When to use

- After any structural change.
- Always after `maintain-repo-index`.
- Part of `audit-alignment`.

## Procedure

1. Walk indexed directories from root README.
2. For each `README.md`: confirm five sections; Parent link correct; Inventory paths exist; Children not inventing files.
3. Ensure Process Caller route table is **not** duplicated in adapters.
4. For `documentation/rules/`: inventory/Children must match area files on disk; `_template.md` may appear in inventory; cross-link *content* is **doc-auditor** responsibility (this agent checks path existence only).
5. Fix or open tasks/GAPS for broken links.
6. No domain invention while repairing structure.
## Gaps

- None structural at healthy baseline; drift is the risk.
