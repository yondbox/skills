# Verification

Verification proves that the overlay did not break the project.

## Common Checks

Run what exists. Do not invent commands without adding them intentionally.

Common categories:

- install
- format check
- lint
- typecheck
- unit tests
- integration tests
- e2e tests
- build
- security checks

## JavaScript / TypeScript

Detect package manager from lockfile.

Typical commands:

- pnpm install --frozen-lockfile
- pnpm lint
- pnpm format:check
- pnpm typecheck
- pnpm test
- pnpm build

Use npm/yarn/bun equivalents when detected.

## Python

Detect uv, poetry, pip, or requirements files.

Typical commands:

- uv sync
- uv run ruff check .
- uv run ruff format --check .
- uv run pytest

## Java / Kotlin

Detect Gradle or Maven.

Typical commands:

- ./gradlew test
- ./gradlew build
- mvn test
- mvn verify

## Android

Typical commands:

- ./gradlew lint
- ./gradlew test
- ./gradlew assembleDebug

## iOS

Typical commands depend on scheme:

- xcodebuild test
- swift test
- swiftlint

## Output

Create `.bootstrap/verification-report.md` with:

- command
- status
- summary
- failure reason
- proposed fix
- whether the failure is caused by overlay changes
