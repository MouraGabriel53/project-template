<!--
Title in Conventional Commits format: <type>(<scope>): <description>
Types: feat, fix, refactor, test, docs, chore, build, ci
Examples: "feat(s7): read multiple PLCs in parallel", "fix: drop expired readings on backfill"
The PR title check fails if the title does not follow this format.
-->

## What changes
<!-- Summary in 1-3 sentences. -->

## Why
<!-- Problem or motivation. Link the issue, if any. -->

## How to test
<!-- Steps to validate locally (e.g. --source s7 --sink mqtt). -->

## Checklist
- [ ] `./mvnw verify` passes locally
- [ ] Layer dependencies respected (ArchitectureTest)
- [ ] No new or upgraded dependency without approval
- [ ] README and example configs updated, if needed
- [ ] Documentation created or updated (docs/, decisions, specs)
