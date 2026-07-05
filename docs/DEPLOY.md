# Deployment Guide

## Required Secrets

Configure these repository secrets in GitHub Settings → Secrets and variables → Actions:

- `SSH_USER` - SSH username for deployment server
- `SSH_HOST` - SSH hostname or IP address
- `SSH_PORT` - SSH port (optional, defaults to 22)
- `SSH_KEY` or `SSH_PRIVATE_KEY` - SSH private key for authentication

## Deployment Path

The infrastructure is deployed to `/opt/dominion/infra` on the remote server.

## Running the Deploy Workflow

The workflow runs automatically on push to `main`. To trigger manually:

1. Go to Actions → Deploy workflow
2. Click "Run workflow"
3. Select branch (usually `main`)
4. Click "Run workflow"

## Reset n8n Admin

To reset the n8n admin user:

```bash
ssh user@host
docker exec -it infra-n8n-1 n8n user-management:reset --email=admin@example.com --password=newpassword
```

## Rollback

To rollback a deployment:

1. Stop containers: `ssh user@host "cd /opt/dominion/infra && sudo docker compose down"`
2. Revert the commit: `git revert <commit-sha>`
3. Push to main or re-run the workflow with the reverted commit
