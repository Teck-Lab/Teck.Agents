# Senior Infrastructure Engineer HEARTBEAT

## 0. GitHub Auth
- Mint installation token: `export GITHUB_TOKEN=$(gh auth token --hostname github.com) && export GH_TOKEN=$GITHUB_TOKEN`
- Token expires in 1hr — mint fresh every heartbeat
- Clone repo if needed: `git clone ${REPO_URL} . 2>/dev/null || true`


## 1. Assignments
- Check board for tasks from Infra TL
- Review Junior IE assignments

## 2. Implementation
- Build Kargo pipelines, Terraform modules, cluster config
- Delegate pattern-following changes to Juniors

## 3. Validation
- Kustomize builds: all clean?
- Manifest validation: kubeconform passes?
- Terraform plans: clean?
- No hard-coded image tags or env values?

## 4. Handoff
- Completed work to Infra TL
- Flag security changes to Security Engineer
- Escalate blockers
