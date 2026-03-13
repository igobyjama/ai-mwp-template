# ai-mwp-template

MWP (Model Workspace Protocol) template for software development workspaces. Copy this repository to start a new workspace.

## What this is

A filesystem-based AI agent workflow following the [Model Workspace Protocol](https://github.com/RinDig/Model-Workspace-Protocol-MWP-). The folder structure replaces framework-level orchestration: numbered stage folders encode execution order, markdown files carry agent instructions, and human review gates separate each stage.

One agent reads the right files at the right stage. No orchestration framework required.

## Workspace structure

```
workspace/
├── CLAUDE.md              # Layer 0: workspace identity and structure map
├── CONTEXT.md             # Layer 1: task routing
├── _config/               # Layer 3: global rules and conventions
├── _shared/               # Layer 3: shared skills and templates
├── setup/                 # new project onboarding
├── _project-template/     # copy this to add a project
└── <project>/             # one folder per project
    ├── repo/              #   cloned git repository (not tracked by workspace git)
    ├── 01_sources/        #   project config and requirements
    ├── 02_development/    #   code changes, tasks, skills
    ├── 03_output/         #   push artifacts
    └── 04_delivery/       #   environment config, deploy plans
```

## Stage pipeline

```
01_sources → [gate 1] → 02_development → [gate 2] → 03_output → [gate 3] → 04_delivery
```

Each gate is a human review point. The agent stops and waits for confirmation.

| Stage | What happens | Human gate |
|-------|-------------|------------|
| 01_sources | Configure project, manage requirements | Confirm repo + config |
| 02_development | Write code, run tests, produce diff | Review diff, approve |
| 03_output | Prepare push checklist and PR description | Execute push, open PR |
| 04_delivery | Deploy to QA and PR preview environments | Confirm environment healthy |

## Multi-project support

Each project is a top-level folder with the same internal structure. The silo name is used throughout.

```
my-api/
my-frontend/
```

## Getting started

### 1. Copy this template

```bash
cp -r ai-mwp-template my-workspace
cd my-workspace
```

### 2. Add a project

```bash
cp -r _project-template my-project
```

Then follow `setup/questionnaire.md`.

### 3. Start working

Open `CONTEXT.md` and tell the agent what you want to do.

## Layer system (from the MWP paper)

| Layer | Files | Purpose | ~Tokens |
|-------|-------|---------|---------|
| 0 | `CLAUDE.md` | Workspace identity | ~500 |
| 1 | `CONTEXT.md` | Task routing | ~300 |
| 2 | `<project>/<stage>/CONTEXT.md` | Stage contract | 300–500 |
| 3 | `_config/`, `_shared/`, `<project>/01_sources/config/` | Stable reference | 500–2k |
| 4 | `<project>/02_development/tasks/`, `<project>/03_output/artifacts/`, `<project>/repo/` | Working artifacts | varies |

Each stage loads only Layers 0–2 plus the Layer 3 and 4 files it declares in its Inputs section. No stage loads the entire workspace.

## License

MIT
