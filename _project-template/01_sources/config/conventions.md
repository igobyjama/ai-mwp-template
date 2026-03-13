# Project Conventions: <project-name>
**Layer 3 — Project Reference**

> Overrides `_config/conventions.md` for this project. Fill in all sections.

## Language and runtime

```
language:
version:
runtime:
```

## Framework and libraries

```
framework:
key-libraries:
```

## Package management

```
package-manager:
install-command:
lock-file:
```

## File and folder naming

```
source-files:       # e.g. camelCase.ts, snake_case.py
test-files:         # e.g. *.test.ts, test_*.py, *_test.go
component-files:    # e.g. PascalCase.tsx
```

## Code naming

```
variables:          # e.g. camelCase
functions:          # e.g. camelCase
classes:            # e.g. PascalCase
constants:          # e.g. SCREAMING_SNAKE_CASE
database-tables:    # e.g. snake_case
```

## Testing

```
test-framework:
test-command:
test-file-location: # e.g. alongside source, __tests__/, tests/
coverage-target:    # e.g. 80%
mock-approach:      # e.g. jest.mock, real DB with test fixtures
```

## Git workflow

```
default-branch:     main
branch-naming:      feat/<description>, fix/<description>, chore/<description>
commit-format:      conventional-commits
merge-strategy:     squash
```

## CI/CD

```
ci-platform:        # e.g. GitHub Actions, GitLab CI
test-in-ci:         yes
lint-in-ci:         yes
build-command:
```

## Notes

> Any conventions that don't fit the fields above.
