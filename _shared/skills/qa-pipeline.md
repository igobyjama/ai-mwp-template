# QA Pipeline
**Layer 3 — Shared Delivery Reference**

This file defines the generic QA deployment pipeline. Project-specific values come from `<project>/04_delivery/config/qa-environment.md`.

## Pipeline steps

### 1. Pre-deployment checks

- [ ] Target branch/tag is confirmed in `<project>/03_output/artifacts/push-checklist.md`
- [ ] All variables listed in `required-env-vars` (from `qa-environment.md`) are set in the environment or secrets manager defined in `secrets-location`
- [ ] QA host is reachable
- [ ] Previous deployment on QA is stable (not mid-deploy or broken)

### 2. Deploy

Fill in the deploy command from `qa-environment.md`:

```bash
# <deploy-command from qa-environment.md>
# Example patterns:
# SSH + Docker:
#   ssh user@qa-host "cd /app && git pull && docker compose up -d --build"
# Fly.io:
#   fly deploy --app <app-name> --env qa
# Kubernetes:
#   kubectl set image deployment/<name> <container>=<image>:<tag>
# Vercel / Netlify:
#   (usually automatic on push — confirm preview URL from platform)
```

### 3. Post-deployment verification

- [ ] Application starts without errors (check logs)
- [ ] Health check endpoint responds: `GET /health` or equivalent
- [ ] Core user flow works (manual smoke test)
- [ ] No unexpected error rates in logs

### 4. Smoke test checklist

Write 3-5 checks specific to the deployed change. Example format:

```
- [ ] <Feature/endpoint under test> returns expected response
- [ ] <User flow> completes without error
- [ ] Database migrations applied successfully (if applicable)
```

### 5. Record result

Update `<project>/04_delivery/CONTEXT.md` deployment history with:
- Date
- Branch/commit deployed
- Result (success / failed / rolled back)
- Notes
