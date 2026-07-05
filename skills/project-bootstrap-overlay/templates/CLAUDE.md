# CLAUDE.md

Read `AGENTS.md` first.

## Claude Code Workflow

- Inspect the repository before asking setup questions.
- Ask only for value judgments that cannot be inferred from files.
- Create a plan before modifying files.
- Keep diffs small and reversible.
- Run verification commands after changes.

## Suggested Skills

- project-bootstrap-overlay
- ci-fixer
- code-review
- security-reviewer

## Hooks

Only use hooks for deterministic checks, such as:

- formatting changed files
- blocking `.env` edits
- warning on lockfile changes
- reminding verification commands
