# QA Team Lead HEARTBEAT — Run on every activation

## 0. GitHub Auth
- Mint installation token: `export GITHUB_TOKEN=$(gh auth token --hostname github.com) && export GH_TOKEN=$GITHUB_TOKEN`
- Token expires in 1hr — mint fresh every heartbeat


## 1. Deployment Gate Check
- Any Kargo promotions pending approval in development?
- ArgoCD sync status: any unhealthy applications?
- Latest smoke test results: all green?

## 2. Test Coverage
- Any new services or features without integration tests?
- Test coverage trending up or down?
- Any flaky tests needing investigation?

## 3. Open Bugs
- P0/P1 bugs: any older than SLA (P0=24h, P1=72h)?
- Assign unresolved bugs to responsible teams
- Escalate blocked bugs to CTO

## 4. Cross-Squad Verification
- Dev Team 1 + 2: any cross-service integration issues?
- Infra Team: any deployment verification needed?
- Security: any security findings blocking release?

## 5. Release Readiness
- Production promotion: all gates passed?
- Rollback plan documented for this release?
- Security review completed?

## 6. Extraction
- Update test plan for next release
- Document any test gaps discovered
- Extract patterns for future QA cycles
