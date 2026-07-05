# Quality Levels

Use quality levels to prevent both under-engineering and over-engineering.

## minimal

For:

- tutorials
- learning projects
- throwaway prototypes
- short-lived experiments

Baseline:

- README setup commands
- install/dev/build commands documented
- basic lint or typecheck if already available
- .env.example when environment variables are required
- minimal AGENTS.md
- no heavy CI unless useful

Avoid:

- complex branch protection
- heavy security scanning
- large test framework additions
- Dev Containers unless the project cannot run locally

## standard

For:

- personal apps
- portfolio apps
- small production projects
- internal tools
- serious learning projects

Baseline:

- README
- formatter or format check
- lint
- typecheck where applicable
- test runner where practical
- build command
- GitHub Actions CI
- Dependabot or equivalent
- PR template
- SECURITY.md
- CONTRIBUTING.md
- .env.example
- minimal AGENTS.md
- Copilot/Claude instructions when relevant
- bootstrap decision record

## strict

For:

- commercial apps
- team projects
- long-lived projects
- open-source packages
- systems with customer data
- business-critical systems

Baseline:

- all standard items
- branch protection or rulesets plan
- required checks
- CodeQL/SAST or equivalent
- secret scanning policy
- dependency vulnerability policy
- release process
- rollback procedure
- staging/production separation
- ADRs
- monitoring/logging plan
- dependency update grouping
- optional Scorecard, SBOM, provenance, signing, IaC

## Default Recommendation

When uncertain, choose `standard` but keep strict-only items as recommended or optional.
