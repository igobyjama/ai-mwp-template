# Skill: Testing
**Layer 3 — Shared Skill**

Load this file when writing tests, running a test suite, or evaluating test coverage.

## Testing principles

- Tests assert **behaviour**, not implementation details
- One assertion per test where practical
- Test names describe what they verify: `it("returns 401 when token is expired")`
- Tests must be deterministic — no random data, no time-dependent assertions without mocking
- Fast tests run first; slow integration tests are isolated

## Test types

| Type | Scope | When to write |
|------|-------|--------------|
| Unit | Single function or class | All new logic |
| Integration | Multiple components together | API endpoints, DB queries |
| E2E | Full user flow | Critical user paths |

## Before writing tests

Read the project's test conventions in `<project>/01_sources/config/conventions.md` to find:
- Test framework in use (Jest, Pytest, Go test, etc.)
- Test file location convention (`*.test.ts`, `*_test.go`, `test_*.py`)
- Mocking approach (real DB vs. mock)
- CI test command

## Running tests

```bash
# Run from the project repo directory
cd <project>/repo/

# Project-specific command — check conventions.md or package.json/Makefile
npm test         # Node.js
pytest           # Python
go test ./...    # Go
```

## Test output in development

Write a `test-results.md` in `<project>/02_development/tasks/` after running tests:

```markdown
## Test results

**Command:** `npm test`
**Date:** YYYY-MM-DD
**Result:** PASS / FAIL

**Failures:**
- `<test name>`: <reason>

**Coverage:** XX% (if available)
```

## Coverage targets

If the project defines coverage targets in its config, enforce them. If not defined, flag any new code with zero test coverage as a review concern.
