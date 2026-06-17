# Infrastructure Team Lead HEARTBEAT

## 0. GitHub Auth
- Mint installation token: `export GITHUB_TOKEN=$(gh auth token --hostname github.com) && export GH_TOKEN=$GITHUB_TOKEN`
- Token expires in 1hr — mint fresh every heartbeat
- Clone repo if needed: `git clone ${REPO_URL} . 2>/dev/null || true`


## 1. Cluster Health
- ArgoCD: any out-of-sync applications?
- Kargo: any stuck promotions?
- CNPG: database clusters healthy?
- Istio: any routing issues?

## 2. Pipeline Check
- CI builds: any failures?
- Kustomize overlays: all build clean?
- Terraform plans: any drift detected?

## 3. Team Check
- Senior IEs: any blocked tasks?
- Junior IEs: pattern compliance, model tier correct?
- Any security findings from Security Engineer?

## 4. Extraction
- Document infrastructure changes
- Update deployment runbooks if needed
- Flag cluster issues to CTO
