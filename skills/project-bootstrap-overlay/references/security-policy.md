# Security Policy

Security setup must match project risk.

## Minimum Baseline

For most projects:

- .gitignore includes environment files
- .env.example exists when env vars are required
- no secrets are committed
- dependencies are updated by Dependabot or equivalent
- CI permissions are least-privilege where possible
- SECURITY.md exists for public or serious projects

## Standard Baseline

For personal public, internal, or small production projects:

- Dependabot or Renovate
- GitHub Actions permissions minimized
- basic dependency vulnerability policy
- CodeQL or equivalent where useful
- secret scanning policy
- PR template includes risk/testing section

## Strict Baseline

For commercial, team, public package, or sensitive projects:

- branch protection/rulesets
- required CI checks
- CodeQL/SAST
- secret scanning and push protection plan
- dependency vulnerability triage policy
- release and rollback plan
- deployment environment separation
- optional SBOM/provenance/signing/Scorecard

## Hard Rules

Never:

- read, print, or modify secrets
- create real secret values
- weaken existing security settings
- broaden GitHub Actions permissions without reason
- auto-run unknown installation scripts
- add third-party actions without noting trust considerations

## GitHub Actions

Prefer:

```yaml
permissions:
  contents: read
```

Increase permissions only when required and document why.

## Dependency Updates

Default:

- Dependabot for small numbers of repositories
- Renovate for many repositories or complex grouping needs

## Auto-merge

Default safe policy:

- no auto-merge for application code
- optional auto-merge for Dependabot patch updates after CI passes
