# Development: <project-name>
**Layer 2 — Stage Contract**

> Replace `<project-name>` throughout this file.

## Purpose

Write all code changes for this project. Work from a requirement, apply project conventions, produce a tested and committable diff.

## Prerequisite

`<project-name>/repo/` is cloned. `<project-name>/01_sources/config/` is complete.

## Inputs

| Layer | File | Purpose |
|-------|------|---------|
| Layer 3 (global) | `_config/workspace-rules.md` | Operating rules |
| Layer 3 (project) | `<project-name>/01_sources/config/conventions.md` | Conventions |
| Layer 3 (project) | `<project-name>/01_sources/config/style-guide.md` | Style rules |
| Layer 3 (project) | `<project-name>/01_sources/config/voice.md` | Comment/commit tone |
| Layer 4 (source) | `<project-name>/repo/` | Project source code |
| Layer 4 (requirement) | `<project-name>/01_sources/requirements/in-progress/REQ-XXX.md` | What to build |
| Layer 4 (task) | `<project-name>/02_development/tasks/<task>.md` | This task's scope (create from `_shared/templates/task-template.md` if absent) |

Load additional skills as needed:

| When | Load |
|------|------|
| Tests | `_shared/skills/testing.md` |
| Git operations | `_shared/skills/git-workflow.md` |
| Reviewing diff | `_shared/skills/code-review.md` |
| Moving requirements | `_shared/skills/requirements.md` |
| Project-specific context | `<project-name>/02_development/skills/<skill>.md` (create on the fly) |

## Process

1. Move the requirement to `01_sources/requirements/in-progress/` now if it is still in `planning/`. Do this before writing any code.
2. If no task file exists for this work, create one from `_shared/templates/task-template.md`.
3. Read the task file and relevant source files.
4. Write changes into `<project-name>/repo/` on a feature branch.
5. Run tests and write results to `<project-name>/02_development/tasks/test-results.md`.
6. Write `<project-name>/02_development/tasks/diff-summary.md` — include REQ-ID, what changed, why.

## Outputs

| File | Location |
|------|----------|
| Code changes | `<project-name>/repo/` (feature branch) |
| `diff-summary.md` | `<project-name>/02_development/tasks/` |
| `test-results.md` | `<project-name>/02_development/tasks/` |

## Active tasks

> Update this table when starting or completing a task. Status values: `active`, `done`, `blocked`.

| Task file | Requirement | Status |
|-----------|------------|--------|
| — | — | — |

## Notes

> Carry-over context: known issues, decisions made, things to revisit.

## Review gate

- [ ] Diff looks correct
- [ ] Tests pass
- [ ] Proceed to `<project-name>/03_output/CONTEXT.md`
