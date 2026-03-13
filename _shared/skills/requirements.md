# Skill: Requirements Management
**Layer 3 — Shared Skill**

Load this file when creating, updating, moving, or reading requirements for a project.

## Where requirements live

```
<project>/01_sources/requirements/
├── planning/       being defined or waiting to start
├── in-progress/    currently being developed
├── done/           completed and accepted
└── cancelled/      will not be implemented
```

For the full convention, see `<project>/01_sources/requirements/CONTEXT.md`.

## Creating a new requirement

1. Determine the next available ID: scan the `requirements/` folder across all state subfolders for the highest existing REQ number, then increment
2. Copy `_shared/templates/requirement-template.md`
3. Rename to `REQ-<ID>-<short-description>.md` in `<project>/01_sources/requirements/planning/`
4. Fill in all sections — at minimum: summary, acceptance criteria, out of scope

## Moving a requirement between states

Move only the **current version** file (highest version number). Leave all previous versions in place.

```bash
# planning → in-progress (work is starting)
mv <project>/01_sources/requirements/planning/REQ-XXX-<name>.md \
   <project>/01_sources/requirements/in-progress/

# in-progress → done (delivered and accepted)
mv <project>/01_sources/requirements/in-progress/REQ-XXX-<name>.md \
   <project>/01_sources/requirements/done/

# any → cancelled
mv <project>/01_sources/requirements/<state>/REQ-XXX-<name>.md \
   <project>/01_sources/requirements/cancelled/
```

Update the **Status** and **Last updated** fields in the requirement file header after moving it.

## Revising a requirement (creating a new version)

When a requirement's scope, criteria, or approach changes significantly:

1. Keep the existing file exactly as it is — it is the version record
2. Copy it to a new file with the next version suffix:
   ```bash
   cp <project>/01_sources/requirements/<state>/REQ-XXX-<name>.md \
      <project>/01_sources/requirements/<state>/REQ-XXX-<name>-v2.md
   ```
3. Update the new file:
   - Increment **Version** field
   - Update **Last updated** date
   - Update **Status** if changed
   - Document the reason in the **Change log** section of both the old and new file

**The old version file is never deleted.** It is the audit trail.

## Reading a requirement for development

Before starting work on a task, load the current version of the relevant requirement as Layer 4 input:

```
Layer 4 (working) | <project>/01_sources/requirements/in-progress/REQ-XXX-<name>.md
```

If development reveals that the requirement needs revision before it can be completed, create a new version first, then proceed.

## Requirement state rules

- A requirement can exist in **exactly one** state folder at any time (current version only)
- Previous versions stay in whatever folder they were last moved to
- IDs are permanent and never reused
- `done/` and `cancelled/` requirements are never moved back to active states — create a new requirement instead
