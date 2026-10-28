<!--
Title in Conventional Commits format: <type>(<scope>): <description>
Types: feat, fix, refactor, test, docs, chore, build, ci
Examples: "feat(order): cancel unpaid orders after 24 hours", "fix(api): return 404 for unknown ids"
The PR title check fails if the title does not follow this format.
-->

## What changes
<!-- Summary in 1-3 sentences. -->

## Why
<!-- Problem or motivation. Link the issue and the spec, if any. -->

## How to test
<!-- Steps to validate locally: commands to run, requests to send, data needed. -->

## Checklist
- [ ] Full test command passes locally (see docs/development.md)
- [ ] Layer dependencies respected (architecture test)
- [ ] No new or upgraded dependency without approval
- [ ] README "Configure" table and `.env.example` updated, if variables changed
- [ ] Documentation created or updated (spec, architecture, api, decisions)
