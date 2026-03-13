# QA Environment: <project-name>
**Layer 3 — Project Reference**

> Fill in all fields. Never store secrets or credential values here — only names and patterns.

## Host

```
qa-host:            # e.g. qa.myapp.example.com, IP, or fly.io app name
qa-url:             # https://qa.myapp.example.com
ssh-user:           # if SSH-based deploy
```

## Deploy method

```
method:             # ssh+docker | kubernetes | fly.io | railway | heroku | custom-script
deploy-command:     # the exact command the human runs
rollback-command:   # how to roll back if deployment fails
```

## Application

```
app-port:
health-check-path:  # e.g. /health, /api/status
startup-timeout:    # seconds to wait for healthy response
```

## Environment variables required

> List variable names only. Values are set in the actual environment or secrets manager.

```
required-env-vars:
  - DATABASE_URL
  - SECRET_KEY
  # add project-specific vars below
```

## Secrets management

```
secrets-location:   # e.g. .env file on server, AWS Secrets Manager, Vault, GitHub secrets
```

## Database / migrations

```
migration-command:  # e.g. "npm run db:migrate" or "python manage.py migrate"
run-migrations:     # yes / no / manual
```

## Smoke test endpoints

> List the URLs to check after deployment to confirm the environment is healthy.

```
smoke-tests:
  - GET /health
  # add more below
```

## Notes
