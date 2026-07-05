# Audit

Audit reviews whether the final setup is safe, useful, and not over-engineered.

## Audit Questions

### Fit

- Does the setup match the project purpose?
- Does the setup match the selected quality level?
- Is anything overkill for this project?
- Is anything missing for the expected deployment risk?

### Safety

- Were secrets avoided?
- Were GitHub Actions permissions minimized?
- Were third-party actions or tools added with justification?
- Is auto-merge conservative?

### Maintainability

- Are scripts and docs consistent?
- Is CI simple enough?
- Are new files necessary?
- Are generated files easy to understand?
- Are decisions recorded?

### AI Agent Quality

- Is AGENTS.md short?
- Are instructions duplicated?
- Are commands accurate?
- Are protected files listed?
- Are skills/hooks limited to useful repeated tasks?

### Existing Project Preservation

- Were generator defaults preserved?
- Were instructor templates preserved?
- Were broad migrations avoided?
- Were large formatting diffs avoided?

## Output

Create `.bootstrap/audit-report.md` with:

- pass/fail summary
- critical issues
- recommended fixes
- optional improvements
- final readiness judgement
