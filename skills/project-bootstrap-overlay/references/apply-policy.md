# Apply Policy

The Apply phase modifies files only after a plan exists and is approved.

## Default Behavior

- apply only required changes
- preserve existing project structure
- preserve generator defaults
- preserve instructor templates
- keep diffs small
- make reversible changes
- do not perform broad migrations

## Risk Levels

### Low Risk

Usually safe after approval:

- create .bootstrap files
- create PR template
- create SECURITY.md
- create CONTRIBUTING.md
- create minimal AGENTS.md
- create .github/copilot-instructions.md
- create .env.example without values

### Medium Risk

Requires explicit explanation:

- modify package.json scripts
- add GitHub Actions
- add Dependabot
- add test framework
- add formatter/linter config
- add Dev Container

### High Risk

Requires explicit user approval:

- migrate ESLint to Biome or the reverse
- change framework version
- change runtime version
- change deployment provider
- modify database/migration setup
- change authentication setup
- change branch protection or repository settings
- add auto-merge

## Never Modify

- .env
- .env.* containing real secrets
- credentials
- private keys
- .git internals
- production deployment secrets

## Patch Strategy

Prefer:

1. create branch
2. apply one domain at a time
3. run verification
4. record decision
5. summarize diff

## Existing Project Rule

For inherited projects, first make the existing project reproducible. Do not modernize aggressively before confirming install, test, and build behavior.
