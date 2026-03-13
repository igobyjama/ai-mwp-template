# Output: <project-name>
**Layer 2 — Stage Contract**

> Replace `<project-name>` throughout this file.

## Purpose

Take human-approved changes and prepare everything needed to push the branch and open a PR. The agent prepares — the human executes.

## Prerequisite

Human has approved the diff in `<project-name>/02_development/tasks/diff-summary.md`.

## Inputs

| Layer | File | Purpose |
|-------|------|---------|
| Layer 3 (global) | `_config/workspace-rules.md` | Operating rules |
| Layer 3 (skill) | `_shared/skills/git-workflow.md` | Push preparation |
| Layer 3 (project) | `<project-name>/01_sources/config/conventions.md` | Commit message format |
| Layer 4 (working) | `<project-name>/02_development/tasks/diff-summary.md` | Approved changes |
| Layer 4 (working) | `<project-name>/02_development/tasks/test-results.md` | Test confirmation |

## Process

1. Write `push-checklist.md` from the approved `diff-summary.md` — human executes this to push the branch.
2. Write `pr-description.md` — ready to paste into GitHub/GitLab.

## Outputs

| File | Location |
|------|----------|
| `push-checklist.md` | `<project-name>/03_output/artifacts/` |
| `pr-description.md` | `<project-name>/03_output/artifacts/` |

## Notes

> Carry-over context: known issues, decisions made, things to revisit before next push.

## Review gate

- [ ] Human reads and executes `push-checklist.md`
- [ ] Human opens PR using `pr-description.md`
- [ ] Push confirmed
- [ ] Proceed to `<project-name>/04_delivery/CONTEXT.md` (skip if `delivery-enabled: no`)
