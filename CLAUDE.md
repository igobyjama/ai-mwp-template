# Workspace Identity
**Layer 0 — Global Identity**

## Structure

```
workspace/
├── CLAUDE.md              ← you are here (Layer 0)
├── CONTEXT.md             ← task routing (Layer 1)
├── _config/               ← global rules and conventions (Layer 3)
├── _shared/               ← shared skills and templates (Layer 3)
├── setup/                 ← new project setup
├── _project-template/     ← copy this to add a project
└── <project>/             ← one folder per project
    ├── repo/              ←   cloned git repository (gitignored)
    ├── 01_sources/        ←   config and requirements
    ├── 02_development/    ←   tasks, skills (created on the fly)
    ├── 03_output/         ←   push artifacts
    └── 04_delivery/       ←   environment config, deploy artifacts
```

## Pipeline

```
01_sources → [gate] → 02_development → [gate] → 03_output → [gate] → 04_delivery
```

Each gate is a human review point. Do not proceed past a gate without confirmation.

## Adding a project

```bash
cp -r _project-template <project-name>
```

Then fill in `<project-name>/01_sources/CONTEXT.md` and follow `setup/questionnaire.md`.

## Layer system

| Layer | Location | Purpose |
|-------|----------|---------|
| 0 | `CLAUDE.md` | Workspace identity |
| 1 | `CONTEXT.md` | Task routing |
| 2 | `<project>/<stage>/CONTEXT.md` | Stage contract (procedure + project paths) |
| 3 | `_config/`, `_shared/`, `<project>/01_sources/config/` | Stable reference |
| 4 | `<project>/02_development/tasks/`, `<project>/03_output/artifacts/`, `<project>/repo/` | Working artifacts this run |

## Workspace scope

One workspace can hold one project or many. Use **one workspace per project** for isolated work. Use a **multi-project workspace** when projects share delivery infrastructure or are developed together (e.g. an API and its frontend). Unrelated projects belong in separate workspaces.

## Key rules

- Load only files listed in the current stage's Inputs table.
- Project config (Layer 3) always lives in `<project>/01_sources/config/`.
- Project-specific skills are created on the fly in `<project>/02_development/skills/`.
- The agent never pushes to remote or deploys. The human does those steps.
