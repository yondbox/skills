# Doctor Phase

The Doctor phase inventories the current state of the project before asking the user questions or changing files.

## Goal

Produce an evidence-based view of the repository:

- what stack it uses
- what environment setup already exists
- what is missing
- what is risky
- what must be preserved
- what should not be changed yet

## Rule

Do not ask the user questions that can be answered by reading repository files.

## Inspect These Files First

Common files:

- README.md
- package.json
- pnpm-lock.yaml / package-lock.json / yarn.lock / bun.lockb
- pyproject.toml / requirements.txt / uv.lock / poetry.lock
- pom.xml / build.gradle / settings.gradle
- go.mod
- Cargo.toml
- Package.swift
- .xcodeproj / .xcworkspace
- AndroidManifest.xml
- Dockerfile / docker-compose.yml
- .devcontainer/devcontainer.json
- .github/workflows/*.yml
- .github/dependabot.yml
- .github/copilot-instructions.md
- AGENTS.md
- CLAUDE.md
- GEMINI.md
- .env.example
- .gitignore
- SECURITY.md
- CONTRIBUTING.md

## Detect

### Project type

Examples:

- web app
- API service
- library
- CLI
- mobile app
- monorepo
- documentation site
- data/ML project
- unknown

### Stack

Detect:

- language
- framework
- runtime
- package manager
- build system
- deploy platform

### Quality setup

Detect:

- formatter
- linter
- type checker
- static analysis
- test runner
- coverage tool
- e2e tool

### CI/CD setup

Detect:

- CI provider
- triggers
- required checks if visible
- deployment workflow
- preview deploys
- production deploys

### Security setup

Detect:

- .env policy
- secret handling
- dependency updates
- vulnerability scanning
- CodeQL/SAST
- GitHub Actions permissions
- third-party actions
- security policy

### AI setup

Detect:

- AGENTS.md
- CLAUDE.md
- Copilot instructions
- Gemini instructions
- skills
- hooks
- MCP configuration
- protected files
- verification expectations

## Output Format

Create `.bootstrap/doctor-report.md` with:

- detected stack
- existing setup
- missing baseline items
- risk areas
- inferred generator/template
- questions that still need human input

Create `.bootstrap/detected-profile.yml` with machine-readable detection output.
