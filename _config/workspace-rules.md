# Workspace Operating Rules
**Layer 3 — Global Reference**

## Core principles

1. **One stage, one job.** Each stage does one thing. Sources stage does not write code. Development stage does not push to remote.
2. **Every output is an edit surface.** Before the next stage runs, a human reads and optionally edits the output.
3. **Plain text as the interface.** All stage communication happens through markdown and JSON files.
4. **Load only what you need.** Each stage reads only the files listed in its Inputs section.
5. **Projects stay in their silos.** A project named `my-api` lives at `my-api/`. Never mix project files across silos.

## Review gates

A review gate is a mandatory human checkpoint between stages. The agent stops and waits.

| Gate | Between stages | Human action |
|------|---------------|--------------|
| Gate 1 | sources → development | Confirm repo is cloned, config looks correct |
| Gate 2 | development → output | Review the diff, approve or request changes |
| Gate 3 | output → delivery | Approve push to remote, confirm target environment |

## Project skills

Project-specific skills (architecture notes, domain knowledge, etc.) are created on the fly in `<project>/02_development/skills/` during development. They are not pre-generated. Create a skill file when the same context would otherwise need to be re-explained across sessions.

## What the agent should never do automatically

- Push to a remote repository
- Merge or delete branches
- Deploy to any environment
- Move output from one project silo into another

## File naming conventions

- Stage context files: `CONTEXT.md` (uppercase, at folder root)
- Config files: lowercase, hyphenated (`style-guide.md`, `voice.md`)
- Task files: lowercase, hyphenated, prefixed with date if helpful (`2024-01-feature-auth.md`)
- Artifact files: descriptive, lowercase (`diff-summary.md`, `push-checklist.md`)

## Git hygiene

- Development always happens on a feature branch, never directly on `main`
- Commit messages follow the project's convention defined in `<project>/01_sources/config/conventions.md`
- See `_shared/skills/git-workflow.md` for branch and commit procedures
