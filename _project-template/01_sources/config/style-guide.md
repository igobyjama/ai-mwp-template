# Style Guide: <project-name>
**Layer 3 — Project Reference**

## Linting

```
linter:             # e.g. ESLint, flake8, golangci-lint
config-file:        # e.g. .eslintrc.json, .flake8
lint-command:
auto-fix-command:
```

## Formatting

```
formatter:          # e.g. Prettier, Black, gofmt
config-file:
format-command:
on-save:            yes/no
```

## Import ordering

```
# Describe the expected import order for this project.
# Example for TypeScript:
# 1. Node built-ins
# 2. External packages
# 3. Internal absolute imports
# 4. Relative imports
```

## Component / module structure

```
# Describe the expected internal structure of a module or component.
# Example:
# 1. Imports
# 2. Types / interfaces
# 3. Constants
# 4. Main export
# 5. Helper functions (unexported)
```

## Patterns to follow

> List architectural or code patterns this project uses consistently.
> Example: repository pattern, command/query separation, compound components.

-

## Patterns to avoid

> List anti-patterns or things previously flagged in review.

-

## Notes

> Link to external style guide if one exists (e.g. Airbnb JS Style Guide, PEP 8).
