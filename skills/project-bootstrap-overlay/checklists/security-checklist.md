# Security Checklist

## Baseline

- [ ] .env files are ignored
- [ ] .env.example exists if env vars are needed
- [ ] no secrets are printed or modified
- [ ] dependency update mechanism exists
- [ ] GitHub Actions permissions are least-privilege where possible
- [ ] SECURITY.md exists for public or serious projects

## Standard

- [ ] Dependabot or Renovate configured
- [ ] CodeQL/SAST considered
- [ ] secret scanning/push protection plan documented
- [ ] PR template includes security/risk section
- [ ] third-party GitHub Actions are reviewed

## Strict

- [ ] branch protection/rulesets plan
- [ ] required checks plan
- [ ] dependency vulnerability triage policy
- [ ] release/rollback process
- [ ] environment separation
- [ ] optional Scorecard/SBOM/provenance/signing considered
