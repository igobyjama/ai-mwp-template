# PR Preview Pipeline
**Layer 3 — Shared Delivery Reference**

This file defines the generic PR preview environment pipeline. Project-specific values come from `<project>/04_delivery/config/pr-environment.md`.

## What a PR environment is

A PR preview environment deploys the feature branch to an isolated, temporary URL so reviewers can interact with the change before merge. It is separate from QA (which tracks the main branch or a stable release branch).

## Pipeline steps

### 1. Confirm PR is open

- [ ] PR URL is available from `<project>/03_output/artifacts/push-checklist.md`
- [ ] PR is open and not in draft state (unless preview is desired for drafts)
- [ ] CI checks are passing or in progress

### 2. Trigger preview deployment

Many platforms deploy PR previews automatically on push. Check `pr-environment.md` to determine which applies:

```bash
# Automatic (Vercel, Netlify, Railway):
#   Nothing to run — check the PR page for the preview URL

# Manual trigger:
# <pr-deploy-command from pr-environment.md>
```

### 3. Retrieve preview URL

- From the PR page (GitHub/GitLab): check the deployment status comment or Checks tab
- From platform CLI: `vercel ls`, `fly releases`, etc.
- From `pr-environment.md` URL pattern if static

### 4. Verify preview

- [ ] Preview URL is accessible
- [ ] Application loads without errors
- [ ] The specific change being reviewed is visible and functional
- [ ] No environment variable errors (missing config)

### 5. Add preview URL to PR

If not automatically posted by the platform, add a comment to the PR:

```
Preview: <url>
```

### 6. Record result

Update `<project>/04_delivery/CONTEXT.md` deployment history with PR number and preview URL.
