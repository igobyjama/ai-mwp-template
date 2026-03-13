# Delivery: <project-name>
**Layer 2 — Stage Contract**

> Replace `<project-name>` throughout this file.

## Purpose

Deploy pushed changes to QA and/or PR preview environments. The agent produces a deployment plan — the human executes it.

## Prerequisite

PR is open. Human confirmed push in Stage 03. Deployment code (scripts, CI configs, IaC) is part of the repository and was developed via Stage 02 like any other code.

## Delivery

```
delivery-enabled: yes
```

> Set to `no` if this project has no QA or PR preview environments. When `no`, the pipeline ends at Stage 03.

## Inputs

| Layer | File | Purpose |
|-------|------|---------|
| Layer 3 (global) | `_config/workspace-rules.md` | Operating rules |
| Layer 3 (skill) | `_shared/skills/qa-pipeline.md` | QA deployment steps |
| Layer 3 (skill) | `_shared/skills/pr-pipeline.md` | PR preview steps |
| Layer 3 (project) | `<project-name>/04_delivery/config/qa-environment.md` | QA host and command |
| Layer 3 (project) | `<project-name>/04_delivery/config/pr-environment.md` | PR preview host |
| Layer 4 (working) | `<project-name>/03_output/artifacts/push-checklist.md` | Branch and PR info |

## Process

**QA deployment:**
1. Read `<project-name>/04_delivery/config/qa-environment.md` and `_shared/skills/qa-pipeline.md`
2. Write `<project-name>/04_delivery/artifacts/qa-deploy-plan.md` with exact steps
3. Stop — human executes

**PR preview:**
1. Read `<project-name>/04_delivery/config/pr-environment.md` and `_shared/skills/pr-pipeline.md`
2. Write `<project-name>/04_delivery/artifacts/pr-deploy-plan.md` with exact steps
3. Stop — human executes

## Environments

| Environment | Config |
|-------------|--------|
| QA | `<project-name>/04_delivery/config/qa-environment.md` |
| PR preview | `<project-name>/04_delivery/config/pr-environment.md` |

## Deployment history

| Date | Type | Branch / PR | Result |
|------|------|------------|--------|
| — | — | — | — |

## Review gate

- [ ] Human executes deployment plan
- [ ] Environment is healthy (smoke test passes)
- [ ] Log result in Deployment history above
