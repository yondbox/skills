# AI Agent Policy

AI setup should help agents work safely without bloating context.

## Principles

- Keep AGENTS.md short.
- Put commands and guardrails before explanation.
- Avoid repeating the same instruction across files.
- Use tool-specific files only for tool-specific differences.
- Prefer CI and scripts over long natural-language rules.
- Use skills for repeatable procedures.
- Use hooks only for deterministic checks.

## File Roles

### AGENTS.md

Cross-agent baseline.

Should include:

- project summary
- install/dev/lint/typecheck/test/build commands
- protected files
- dependency rules
- verification expectation

### CLAUDE.md

Claude Code-specific notes.

Should include:

- reference to AGENTS.md
- allowed hooks or skills
- tool-specific workflow expectations

### .github/copilot-instructions.md

GitHub Copilot-specific notes.

Should include:

- repository-specific build/test/validation expectations
- short coding preferences
- reference to AGENTS.md when appropriate

### GEMINI.md

Gemini-specific notes, only if Gemini CLI is used.

## Hooks

Good hooks:

- format changed files
- block .env edits
- warn on lockfile changes
- remind verification commands

Bad hooks:

- design decisions
- broad refactoring
- running untrusted commands
- hidden network access
- automatic code approval

## Subagents

Useful subagents:

- security reviewer
- CI reviewer
- docs reviewer
- test reviewer
- migration planner

Avoid creating subagents unless there is a repeated task.
