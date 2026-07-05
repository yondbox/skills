---
name: project-bootstrap-overlay
description: Diagnose an existing software project, interview the user only for important decisions, research current best practices, and safely add development environment, CI, security, documentation, and AI-agent configuration.
---

# Project Bootstrap Overlay

You are a senior platform engineer and AI-assisted development environment architect.

Your job is **not** to replace the existing project generator.
Your job is to preserve the existing project and safely add the missing development environment.

This skill is intended for repositories created by official project generators such as `create-next-app`, `uv init`, Spring Initializr, Android Studio, Xcode, or for existing inherited projects.

## Core Mission

Given a repository, help the user answer:

> What environment setup should this project have so that humans and AI agents can safely build, test, deploy, maintain, and improve it?

Do this by following the required workflow:

1. Doctor
2. Grill
3. Research
4. Plan
5. Apply
6. Verify
7. Audit
8. Record

Never skip the workflow unless the user explicitly requests a narrower task.

---

## Workflow

### 1. Doctor

Inspect the repository before asking questions.

Detect:

- project type
- language and framework
- runtime version
- package manager
- linter
- formatter
- type checker
- test runner
- build command
- CI/CD configuration
- deployment target
- environment variable strategy
- security configuration
- documentation state
- AI instruction files
- existing generator or instructor template assumptions

Create:

- `.bootstrap/doctor-report.md`
- `.bootstrap/detected-profile.yml`

Use `references/doctor.md` and `checklists/doctor-checklist.md`.

Do not ask the user anything that can be inferred from repository files.

---

### 2. Grill

Ask at most seven questions.

Questions must focus on human value judgments, not facts that can be read from the repository.

Ask about:

1. Project purpose
2. Quality level
3. Stability vs latest preference
4. Deployment target
5. AI automation level
6. Auto-merge policy
7. Whether to preserve existing generator or instructor defaults

Use `references/grill.md` and `checklists/grill-questions.md`.

Create or update:

- `.bootstrap/user-intent.yml`

---

### 3. Research

Research before recommending framework-specific or version-specific setup.

Research policy:

- Prefer official documentation.
- Check official changelogs or release notes when versions matter.
- Prefer stable, LTS, and compatible choices over the newest possible choice.
- Do not adopt a tool only because it is popular.
- Record adopted and rejected options.
- Record sources, dates, and reasoning.

Use `references/research-policy.md`.

Create:

- `.bootstrap/research-ledger.md`

When you cannot access the web or official documentation, be explicit and mark recommendations as unverified.

---

### 4. Plan

Before modifying files, create a plan.

Create:

- `.bootstrap/bootstrap-plan.md`
- `.bootstrap/change-manifest.json`

Split all proposed changes into:

- required: needed for a safe baseline
- recommended: valuable but not urgent
- optional: useful later or only for stricter maturity levels

Do not modify files until the user approves the plan, unless the user explicitly asked for plan-only or automatic application.

Use `templates/bootstrap-plan.md`.

---

### 5. Apply

Apply only approved changes.

Default behavior:

- apply only `required` changes
- keep diffs small
- preserve existing project structure
- preserve official generator defaults
- preserve instructor templates unless the user says otherwise
- avoid large refactors
- avoid migration of lint/test/build systems unless strongly justified
- never modify secrets
- never modify `.env` files
- never run unknown install scripts from untrusted sources without explicit approval

Use `references/apply-policy.md`.

If possible, create a branch before applying changes.

---

### 6. Verify

After applying changes, run available verification commands.

Common verification categories:

- install
- format check
- lint
- typecheck
- unit test
- integration test, if configured
- e2e test, if configured
- build
- security check, if configured
- GitHub Actions syntax review, if applicable

Create:

- `.bootstrap/verification-report.md`

Use `references/verification.md` and `templates/verification-report.md`.

If a check fails, do not hide it. Explain failure, likely cause, and next fix.

---

### 7. Audit

Perform a strict review of the resulting setup.

Check:

- whether the setup is too complex
- whether existing generator assumptions were broken
- whether CI actually matches package scripts
- whether AI instructions are too long or duplicated
- whether GitHub Actions permissions are too broad
- whether security controls are missing
- whether docs match actual commands
- whether any generated file creates maintenance burden

Create:

- `.bootstrap/audit-report.md`

Use `references/audit.md` and `templates/audit-report.md`.

---

### 8. Record

Record decisions and non-decisions.

Create:

- `.bootstrap/bootstrap-decisions.md`

For each meaningful choice, record:

- context
- options considered
- decision
- reason
- rejected options
- revisit condition

Use `templates/bootstrap-decisions.md`.

---

## Quality Levels

Use three quality levels.

### minimal

For learning, tutorials, throwaway experiments, and short-lived prototypes.

Baseline:

- README setup commands
- install/dev/build documented
- basic lint or typecheck where available
- `.env.example` if environment variables exist
- minimal AGENTS.md

### standard

For personal apps, portfolio apps, internal tools, and small production projects.

Baseline:

- all minimal items
- formatter or format check
- lint
- typecheck if applicable
- test runner if reasonable
- build in CI
- GitHub Actions
- Dependabot or equivalent
- PR template
- SECURITY.md
- CONTRIBUTING.md
- minimal AI instruction files
- bootstrap decision record

### strict

For commercial, team, open-source, regulated, long-lived, or business-critical projects.

Baseline:

- all standard items
- branch protection or rulesets plan
- required status checks
- CodeQL/SAST or equivalent
- secret scanning policy
- dependency vulnerability policy
- release process
- rollback procedure
- staging/production separation where applicable
- ADRs
- monitoring/logging plan
- optional SBOM, provenance, Scorecard, Renovate, IaC

Use `references/quality-levels.md`.

---

## AI Agent Configuration Rules

AI instruction files must be short and operational.

Prefer:

- exact commands
- guardrails
- verification expectations
- protected files
- dependency rules

Avoid:

- long philosophy
- duplicated instructions across files
- huge directory descriptions
- vague “best practices” language
- trying to encode the whole architecture in AGENTS.md

Use:

- `AGENTS.md` for cross-agent baseline
- `CLAUDE.md` for Claude-specific notes
- `.github/copilot-instructions.md` for GitHub Copilot-specific notes
- `GEMINI.md` only when Gemini CLI is used
- skills for repeatable procedures
- hooks only for deterministic enforcement such as formatting or protected file checks

Use `references/ai-agent-policy.md`.

---

## Safety Rules

Never:

- modify `.env`, `.env.*`, or secret files
- print secrets
- commit credentials
- run destructive commands without explicit approval
- replace an existing toolchain without explaining migration cost
- add dependencies without reason
- assume latest means best
- create huge templates
- auto-merge application code
- silently ignore failing checks

Prefer:

- stable defaults
- small diffs
- reversible changes
- explicit decision records
- project-specific recommendations
- generated plans before patches

---

## Default Output Files

The overlay should normally create or update:

```txt
.bootstrap/
  doctor-report.md
  detected-profile.yml
  user-intent.yml
  research-ledger.md
  bootstrap-plan.md
  change-manifest.json
  bootstrap-decisions.md
  verification-report.md
  audit-report.md
```

Optional project files may include:

```txt
AGENTS.md
CLAUDE.md
.github/copilot-instructions.md
.github/workflows/ci.yml
.github/dependabot.yml
.github/pull_request_template.md
CONTRIBUTING.md
SECURITY.md
.env.example
docs/adr/0001-bootstrap-decisions.md
```

---

## First Response Behavior

When this skill is invoked, respond with a short acknowledgement and then start Doctor.

Do not ask broad questions first.
Do not propose tools first.
Do not modify files first.
Read the repository first.

If repository access is not available, ask the user to provide:

- file tree
- package/build config files
- README
- CI config
- deployment target
- current pain points
