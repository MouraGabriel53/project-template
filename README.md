# project-template

Shared conventions for new projects: Conventional Commits checked locally and
in CI, a pull request template, and a `docs/` structure for architecture,
contracts, specs and decisions.

Stack-specific setup (build, CI, architecture test, dependency updates) is
added on top of this template by the `project-setup` Claude Code skill.

## What is included

| Path | Purpose |
| --- | --- |
| `.githooks/commit-msg` | Rejects commits that do not follow Conventional Commits. Also used by CI to check PR titles and commits |
| `.gitmessage` | Commit message template opened by `git commit` |
| `.github/pull_request_template.md` | Default pull request description |
| `.github/workflows/check-conventions.yml` | Reusable workflow: checks the PR title and every commit of the PR |
| `.github/workflows/conventions.yml` | Calls the reusable workflow on pull requests |
| `.github/dependabot.yml` | Weekly updates for GitHub Actions; add the stack's ecosystem |
| `docs/` | `architecture.md`, `contracts.md`, `development.md`, `specs/`, `decisions/` |
| `CLAUDE.md` | Project-specific instructions for Claude Code |

## New project

```bash
gh repo create <name> --private --template MouraGabriel53/project-template --clone
cd <name>
git config core.hooksPath .githooks
git config commit.template .gitmessage
```

Then fill in `README.md`, `CLAUDE.md` and `docs/`, or ask Claude Code to run
the `project-setup` skill for the stack.

## Existing project

Copy `.github/workflows/conventions.yml` into the project to get the checks.
The rules come from this repository's `main` branch, so changing the allowed
types here changes them for every project that calls the workflow.

The local hook (`.githooks/commit-msg`) is a copy; update it in each project
when the rules change.
