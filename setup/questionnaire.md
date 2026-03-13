# New Project Setup
**Workspace Setup**

Fill in Part 1, then follow the setup steps in Part 2.

---

## Part 1 — Project information

**Project name** (silo folder name — lowercase, hyphenated):
```
project-name:
```

**One-line description:**
```
description:
```

**Repository URL:**
```
repo-url:
```

**Default branch:**
```
default-branch: main
```

**Language / framework / package manager:**
```
language:
framework:
package-manager:
```

**Test framework and run command:**
```
test-framework:
test-command:
```

**Linter and formatter:**
```
linter:
formatter:
```

**Branch / commit / merge strategy:**
```
branch-naming:   feat/<desc>, fix/<desc>
commit-format:   conventional-commits
merge-strategy:  squash
```

**QA environment:**
```
qa-host:
qa-deploy-method:
qa-deploy-command:
```

**PR preview environment:**
```
pr-host:
pr-deploy-method:
pr-deploy-command:
```

**Environment variable names** (names only — no values here):
```
env-vars:
  -
```

**Code style and tone notes:**
```
style-notes:
tone:
```

---

## Part 2 — Setup steps

### 1. Create project silo

```bash
cp -r _project-template <project-name>
grep -rl '<project-name>' <project-name> | xargs sed -i 's/<project-name>/<actual-name>/g'
```

- [ ] `<project-name>` placeholder replaced throughout the silo

### 2. Fill in project config

Using your answers from Part 1:

- [ ] `<project>/01_sources/CONTEXT.md` — repo URL, language, framework
- [ ] `<project>/01_sources/config/conventions.md` — language, test command, branch/commit rules
- [ ] `<project>/01_sources/config/style-guide.md` — linter, formatter, patterns
- [ ] `<project>/01_sources/config/voice.md` — tone, commit style
- [ ] `<project>/04_delivery/config/qa-environment.md` — QA host and deploy command
- [ ] `<project>/04_delivery/config/pr-environment.md` — PR preview host and deploy command

### 3. Clone the repository

```bash
git clone <repo-url> <project-name>/repo/
```

- [ ] Clone succeeded, repo is readable

### 4. Create initial requirements

In `<project>/01_sources/requirements/planning/`:
- Copy `_shared/templates/requirement-template.md` for each requirement
- Name each file `REQ-001-<description>.md`, incrementing the ID

- [ ] At least one requirement exists in `planning/`

### 5. Register the project

- [ ] Add project to the Active projects table in `CONTEXT.md`

### Ready

Proceed to `<project>/02_development/CONTEXT.md`.
