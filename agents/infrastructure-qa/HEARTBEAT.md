# Infrastructure QA HEARTBEAT — Run on scheduled cadence

## 0. GitHub Auth
- Mint installation token: `export GITHUB_TOKEN=$(gh auth token --hostname github.com) && export GH_TOKEN=$GITHUB_TOKEN`
- Token expires in 1hr — mint fresh every heartbeat
- Clone repo if needed: `git clone ${REPO_URL} . 2>/dev/null || true`

## 1. Cluster Health Check
- All nodes healthy? `kubectl get nodes`
- All pods running? `kubectl get pods --all-namespaces --field-selector=status.phase!=Running`
- Any CrashLoopBackOff or ImagePullBackOff? Escalate to Infra TL

## 2. ArgoCD Sync Status
- All applications synced and healthy? `argocd app list`
- Out-of-sync apps: any drift detected?
- Kargo promotions: stuck freight? Check warehouse subscription

## 3. Resource Utilization
- Node disk/memory pressure?
- PVC usage: any volumes >80%?
- Longhorn volume health: degraded replicas?

## 4. Security Posture
- Cert-manager certificates: any near expiry (<7 days)?
- ESO ExternalSecrets: all healthy?
- Istio mTLS: any permissive mode drift?

## 5. Backup Verification
- CNPG backup status: latest backup succeeded?
- Longhorn backup status: all volumes backed up?
- Test restore of critical databases

## 6. CI Watch
- Check latest Teck.GitOps / Teck.Terraform CI builds
- Any failed ArgoCD syncs? Report to Infra TL
- Terraform plan drift: any unapplied changes?

## 7. Extraction
- Document cluster health trends
- Update runbook for any new failure modes
- On completion: wake QA Team Lead (POST /api/agents/{qa-tl-id}/wakeup)
