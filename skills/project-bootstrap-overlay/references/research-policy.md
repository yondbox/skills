# Research Policy

Use this policy before making framework-specific, deployment-specific, security-specific, or version-specific recommendations.

## Priority of Sources

1. Official documentation
2. Official changelog or release notes
3. Official examples or starter templates
4. Standards bodies or project-maintained best practices
5. Trusted vendor docs
6. High-quality engineering articles
7. Community discussions only as secondary evidence

## Selection Principles

Prefer:

- stable releases
- LTS versions
- generator defaults
- official recommendations
- low-maintenance setups
- compatibility with existing project files
- reversible changes

Avoid:

- newest version by default
- migration for style preference only
- tools that duplicate existing tools
- complex setups without strong need
- unofficial workarounds when official support exists

## Required Research Output

Create `.bootstrap/research-ledger.md` with:

- topic researched
- sources consulted
- date of consultation
- options considered
- recommendation
- rejected options
- confidence level
- open questions

## Confidence Levels

- high: official docs and repository evidence agree
- medium: official docs are clear but repository has unknowns
- low: no current official source was available or assumptions are required

## When Web Access Is Unavailable

State clearly:

- that current official information could not be verified
- which recommendations are based on repository evidence only
- what the user should verify manually
