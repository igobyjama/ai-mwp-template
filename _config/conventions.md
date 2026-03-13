# Default Coding Conventions
**Layer 3 — Global Reference**

> This file contains workspace-wide defaults. Project-specific overrides live in
> `<project>/01_sources/config/conventions.md` and take precedence.

## General

- UTF-8 encoding for all files
- LF line endings
- Trailing newline at end of every file
- No trailing whitespace

## Naming

| Element | Convention | Example |
|---------|-----------|---------|
| Files | lowercase, hyphenated | `user-service.ts` |
| Folders | lowercase, hyphenated | `auth-middleware/` |
| Environment variables | SCREAMING_SNAKE_CASE | `DATABASE_URL` |
| Constants | SCREAMING_SNAKE_CASE | `MAX_RETRY_COUNT` |

## Commit messages

Format: `<type>(<scope>): <short description>`

Types: `feat`, `fix`, `refactor`, `test`, `docs`, `chore`, `ci`

Example: `feat(auth): add JWT refresh token endpoint`

- Subject line: 72 characters max
- Use imperative mood ("add" not "added")
- Reference issue numbers where applicable: `fix(api): handle null user (#42)`

## Comments

- Write comments for intent, not mechanics
- Avoid obvious comments (`// increment counter`)
- Prefer self-documenting names over comments

## Branch naming

`<type>/<short-description>` — Example: `feat/user-auth`, `fix/null-pointer-login`

## Pull requests

- One logical change per PR
- PR description explains the why, not just the what
- All tests pass before requesting review
- Link to relevant issue or ticket

---

> Replace or extend this file with project-specific conventions in
> `<project>/01_sources/config/conventions.md`.
