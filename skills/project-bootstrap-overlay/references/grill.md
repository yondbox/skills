# Grill Phase

The Grill phase asks the user only for value judgments that cannot be inferred from repository files.

## Goal

Capture intent, risk tolerance, quality target, and automation preferences.

## Rule

Ask at most seven questions.

Do not ask about:

- framework if it can be detected
- package manager if lockfiles exist
- linter if config files exist
- deployment if config files clearly indicate it
- test runner if scripts or config files exist

## Core Questions

1. What is the project purpose?
   - learning
   - personal
   - portfolio
   - internal
   - commercial
   - open-source

2. What quality level do you want?
   - minimal
   - standard
   - strict

3. What is your stability preference?
   - stable: prefer proven, low-change tools
   - balanced: current stable defaults
   - latest: adopt newer tools when justified

4. What deployment target should this project optimize for?
   - none
   - Vercel
   - Cloudflare
   - AWS
   - Firebase
   - Docker
   - unknown

5. How much may AI agents change?
   - suggest only
   - plan only
   - apply after approval
   - safe auto-apply

6. What auto-merge policy do you want?
   - none
   - Dependabot patch only
   - Dependabot minor and patch
   - docs only

7. Should the existing generator or instructor template be preserved?
   - yes
   - no

## Output

Create `.bootstrap/user-intent.yml`.

## Example

```yaml
project:
  purpose: learning
  preserveExistingTemplate: true

quality:
  level: standard
  stability: balanced

deployment:
  target: vercel

automation:
  aiChangePermission: apply_after_approval
  autoMerge: dependabot_patch_only
```
