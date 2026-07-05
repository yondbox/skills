# AGENTS.md

## Project

Preserve the existing project structure unless a change is explicitly requested.
Prefer small, reviewable changes over broad refactors.

## Commands

Replace placeholders with detected commands.

- Install: `<install command>`
- Dev: `<dev command>`
- Format check: `<format check command>`
- Lint: `<lint command>`
- Typecheck: `<typecheck command>`
- Test: `<test command>`
- Build: `<build command>`

## Rules

- Do not add dependencies without explaining why.
- Do not modify secrets or environment files.
- Do not change public APIs without updating docs and tests.
- Do not replace existing toolchains without explaining migration cost.
- Run available verification commands before reporting completion.
- Update documentation when behavior or setup changes.

## Protected Files

Do not modify without explicit approval:

- `.env`
- `.env.*`
- credential files
- private keys
- production deployment secrets
- `.git/**`
