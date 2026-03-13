# Skill: Code Review
**Layer 3 — Shared Skill**

Load this file when reviewing a diff or evaluating code quality before approving output.

## Review checklist

### Correctness
- [ ] Does the code do what the task description says it should do?
- [ ] Are edge cases handled (null, empty, overflow, concurrent access)?
- [ ] Are error paths handled explicitly?
- [ ] Are external inputs validated at system boundaries?

### Security
- [ ] No secrets, credentials, or tokens in code or comments
- [ ] SQL queries use parameterised inputs, not string concatenation
- [ ] User input is sanitised before use in HTML, shell, or file paths
- [ ] New routes or data access paths: authentication and authorization are applied
- [ ] New dependencies: run the project's audit command (e.g. `npm audit`, `pip-audit`, `go mod verify`) and flag any high/critical findings
- [ ] Dependencies are from trusted sources and at expected versions

### Quality
- [ ] Names are descriptive and consistent with project conventions
- [ ] No commented-out dead code
- [ ] No unnecessary complexity or premature abstraction
- [ ] Functions do one thing

### Tests
- [ ] New logic has test coverage
- [ ] Tests assert behaviour, not implementation
- [ ] Existing tests still pass

### Diff hygiene
- [ ] No unintended whitespace or formatting changes mixed with logic changes
- [ ] No debug statements left in (`console.log`, `print`, `debugger`)
- [ ] No TODO comments left unaddressed unless explicitly deferred

## Output format

When completing a review, write a `review-summary.md` in `<project>/03_output/artifacts/` with:

```markdown
## Review summary

**Status:** Approved / Changes requested

**Issues found:**
- [CRITICAL] ...
- [MINOR] ...

**Approved with notes:**
- ...
```
