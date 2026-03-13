# Sources: <project-name>
**Layer 2 — Stage Contract**

> Replace `<project-name>` throughout this file.

## Identity

| Field | Value |
|-------|-------|
| Project name | `<project-name>` |
| Repo URL | `<repo-url>` |
| Default branch | `main` |
| Language | `<language>` |
| Framework | `<framework>` |

## Paths

| Resource | Path |
|----------|------|
| Repository | `<project-name>/repo/` |
| Conventions | `<project-name>/01_sources/config/conventions.md` |
| Style guide | `<project-name>/01_sources/config/style-guide.md` |
| Voice | `<project-name>/01_sources/config/voice.md` |
| Requirements | `<project-name>/01_sources/requirements/` |

## Purpose

Acquire and configure project source material: clone or pull the repository, maintain project config (conventions, style, voice), and manage requirements.

## Inputs

| Layer | File | Purpose |
|-------|------|---------|
| Layer 3 (global) | `_config/workspace-rules.md` | Operating rules |
| Layer 3 (skill) | `_shared/skills/git-workflow.md` | Clone/pull procedures |
| Layer 3 (skill) | `_shared/skills/requirements.md` | Requirements procedures |
| Layer 3 (template) | `_shared/templates/requirement-template.md` | New requirement form |
| Layer 4 (setup) | `setup/questionnaire.md` | Project info (new project only) |

## Process

**Clone new project:**
1. Read `setup/questionnaire.md` for project details
2. `git clone <repo-url> <project-name>/repo/`
3. Fill in `<project-name>/01_sources/config/conventions.md`, `<project-name>/01_sources/config/style-guide.md`, `<project-name>/01_sources/config/voice.md`
4. Update Identity table and Status log below

**Pull update:**
1. `cd <project-name>/repo/ && git pull origin <branch>`
2. Note changes (new deps, migrations) in Status log below

**Requirements:** see `_shared/skills/requirements.md`
- New: copy template → `01_sources/requirements/planning/REQ-<ID>-<name>.md`
- Move state: move current version file, update file header
- Revise: copy current → `REQ-<ID>-<name>-v2.md`, update change log in both

## Status

| Date | Operation | Notes |
|------|-----------|-------|
| — | not cloned | — |

## Review gate

- [ ] Repo is cloned and readable
- [ ] Config files are complete
- [ ] Proceed to `<project-name>/02_development/CONTEXT.md`
