# project-template

Shared conventions for new projects: Conventional Commits checked locally and
in CI, a pull request template, a README skeleton, and a `docs/` structure in
pt-BR for architecture, API, contexts with one spec per operation, and
decisions.

Stack-specific setup (build, CI, architecture test, dependency updates) is
added on top of this template by the `project-setup` Claude Code skill. Web
apps start from
[`project-template-web`](https://github.com/MouraGabriel53/project-template-web)
instead; both share the same README, docs layout and commit rules.

This file describes the template. Delete it when the project is created.

## What is included

| Path | Purpose |
| --- | --- |
| `README.md` | Project README skeleton: pitch, getting started (prerequisites, clone, configure, run), links to docs |
| `.env.example` | Every variable the app reads; secrets left empty. Mirrors the README "Configure" table |
| `CLAUDE.md` | Project-specific instructions for Claude Code |
| `.githooks/commit-msg` | Rejects commits that do not follow Conventional Commits. Also used by CI to check PR titles and commits |
| `.gitmessage` | Commit message template opened by `git commit` |
| `.github/pull_request_template.md` | Default pull request description |
| `.github/workflows/check-conventions.yml` | Reusable workflow: checks the PR title and every commit of the PR |
| `.github/workflows/conventions.yml` | Calls the reusable workflow on pull requests |
| `.github/dependabot.yml` | Weekly updates for GitHub Actions; add the stack's ecosystem |
| `docs/` | `README.md` (index), `architecture.md`, `api.md`, `development.md`, `decisions/`, `_templates/` (context, operation, decision) |

## New project

```bash
gh repo create <name> --private --template MouraGabriel53/project-template --clone
cd <name>
git config core.hooksPath .githooks
git config commit.template .gitmessage
rm TEMPLATE.md
```

Then fill in `README.md`, `.env.example`, `CLAUDE.md` and `docs/`, or ask
Claude Code to run the `project-setup` skill for the stack.

## Existing project

Copy `.github/workflows/conventions.yml` into the project to get the checks.
The rules come from this repository's `main` branch, so changing the allowed
types here changes them for every project that calls the workflow, including
the ones created from `project-template-web`.

The local hook (`.githooks/commit-msg`) is a copy; update it in each project,
and in `project-template-web`, when the rules change.
