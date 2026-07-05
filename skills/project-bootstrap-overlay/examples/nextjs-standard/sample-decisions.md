# Sample Bootstrap Decisions: Next.js Standard

## Decision 001: Preserve Existing Linter

### Context

The project was created by an official generator or instructor template and already includes lint configuration.

### Options Considered

1. Preserve existing linter
2. Migrate to Biome
3. Add Prettier alongside existing linter

### Decision

Preserve the existing linter for the initial overlay.

### Reason

The first goal is to make the project safely verifiable without increasing migration risk or creating large formatting diffs.

### Rejected Options

Biome migration may be considered later, but it is not required for the initial bootstrap.

### Revisit When

Revisit after the learning phase or before production hardening.

## Decision 002: Use Simple GitHub Actions CI First

### Context

No CI exists yet.

### Options Considered

1. Add local `.github/workflows/ci.yml`
2. Use reusable workflow immediately
3. Skip CI for now

### Decision

Add local `.github/workflows/ci.yml`.

### Reason

This is the fastest way to verify lint, typecheck, test, and build. Reusable workflows become valuable after multiple repositories repeat the same setup.

### Rejected Options

Reusable workflow is premature for the first repository.

### Revisit When

Revisit after 3 or more projects use the same CI pattern.
