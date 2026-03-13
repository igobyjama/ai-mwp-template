# Requirement Template
**Layer 3 — Shared Template**

Copy this file into `<project>/01_sources/requirements/planning/` when creating a new requirement. Rename it to `REQ-<ID>-<short-description>.md`. Fill in all sections before moving to `in-progress/`.

---

```markdown
# REQ-<ID>: <Title>

**Version:** v1
**Status:** planning
**Created:** YYYY-MM-DD
**Last updated:** YYYY-MM-DD

## Summary

> One paragraph: what this requirement asks for and why it is needed.

## Context and motivation

> What problem does this solve? Who requested it? What happens without it?

## Acceptance criteria

Each criterion must be testable. When all boxes can be checked, the requirement is done.

- [ ] ...
- [ ] ...
- [ ] ...

## Out of scope

> Explicitly list what this requirement does NOT cover to prevent scope creep.

-

## Dependencies

> Other requirements or external things that must be complete before this can start or finish.

| Dependency | Type | Status |
|-----------|------|--------|
| REQ-XXX | blocking / related | planning / done |

## Technical notes

> Constraints, implementation hints, or architectural decisions relevant to this requirement.
> Leave blank if unknown at planning time.

## Open questions

> Things that need answers before or during development. Resolve before moving to `done/`.

- [ ] ...

## Change log

> When a new version (v2, v3...) is created, record why here in both the old and new file.

| Version | Date | Changed by | Reason for change |
|---------|------|-----------|------------------|
| v1 | YYYY-MM-DD | | Initial version |
```
