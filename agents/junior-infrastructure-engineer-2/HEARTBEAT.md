# Junior Infrastructure Engineer 2 HEARTBEAT — Run on schedule and task assignment

## 0. GitHub Auth
- Mint installation token: `export GITHUB_TOKEN=$(gh auth token --hostname github.com) && export GH_TOKEN=$GITHUB_TOKEN`
- Token expires in 1hr — mint fresh every heartbeat
- Clone repo if needed: `git clone ${REPO_URL} . 2>/dev/null || true`

## 1. Task Check
- Check assigned tasks from Infra Senior or Infra TL
- No tasks? Monitor cluster health and report to Infra Senior
- Blocked? Escalate to Infra Senior immediately

## 2. Execute Tasks
- For each assigned task:
  - GitOps changes: create Kustomize overlay, verify with `kustomize build`
  - Terraform changes: `tofu plan`, verify no drift
  - Runbook tasks: follow SOP exactly, never improvise
  - Verify: `kubectl apply --dry-run=server` before any deployment

## 3. Pre-Commit Gate (MANDATORY)
- `kustomize build {overlay}` — must succeed
- `tofu plan` — must show expected changes only
- `kubectl apply --dry-run=server -f {manifest}` — must validate
- Never commit without passing ALL checks

## 4. Extraction
- Document any issues encountered
- Update runbook if procedures changed
- On completion: wake Infra Senior (POST /api/agents/{infra-senior-id}/wakeup)
