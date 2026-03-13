# PR Preview Environment: <project-name>
**Layer 3 — Project Reference**

> Fill in all fields. Never store secrets or credential values here — only names and patterns.

## Platform

```
platform:           # vercel | netlify | railway | fly.io | render | custom
automatic-deploy:   # yes / no (does the platform auto-deploy on PR push?)
```

## Preview URL pattern

```
# How to find the preview URL for a given PR.
# Example patterns:
# Vercel:   https://<project>-git-<branch>-<org>.vercel.app
# Netlify:  https://deploy-preview-<pr-number>--<site-name>.netlify.app
# Custom:   https://pr-<pr-number>.preview.myapp.example.com
url-pattern:
```

## Manual deploy command

> If not automatic, the command the human runs to trigger a preview deployment.

```
deploy-command:
```

## Environment variables for preview

> Variable names that must be set in the preview environment. Values are in the platform's secret store.

```
required-env-vars:
  - DATABASE_URL
  # add project-specific vars below
```

## Limitations

> Things that are different in preview vs. production (e.g. no background jobs, read-only DB, no email sending).

-

## Notes
