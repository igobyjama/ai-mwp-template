# Skill: Git Workflow
**Layer 3 — Shared Skill**

Load this file when performing any git operation: cloning, branching, committing, or preparing a push.

## Clone a project repository

```bash
git clone <repo-url> <project>/repo/
```

After cloning, verify:
- Default branch is what you expect (`main` or `master`)
- `.gitignore` is present
- Note the remote URL for later push operations

## Create a feature branch

Always branch from the project's default branch. Never commit directly to `main`.

```bash
cd <project>/repo/
git checkout main
git pull origin main
git checkout -b feat/<short-description>
```

Branch naming: `<type>/<description>` — see `_config/conventions.md`.

## Development workflow

Work happens in `<project>/02_development/tasks/`. When changes are ready:

1. Apply changes to the repo in `<project>/repo/`
2. Stage only the intended files — never `git add .` blindly
3. Review the staged diff before committing

```bash
git diff --staged
```

## Commit

```bash
git commit -m "feat(scope): short description

Longer explanation if needed. Reference issue numbers.

Co-authored-by: Claude <noreply@anthropic.com>"
```

Never use `--no-verify` or `--no-gpg-sign` unless explicitly instructed.

## Prepare for push (03_output stage)

Write a `push-checklist.md` in `<project>/03_output/artifacts/`:

```markdown
## Push checklist

- [ ] Branch: `feat/<name>`
- [ ] Target remote: `origin`
- [ ] Target base branch: `main`
- [ ] Commits to push: N
- [ ] Tests passing: yes/no
- [ ] Review gate: approved
```

**The agent does not push.** The human executes the push after reviewing the checklist.

## After human pushes

The human confirms push succeeded. Then proceed to `<project>/04_delivery/CONTEXT.md`.
