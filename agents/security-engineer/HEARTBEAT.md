# Security Engineer HEARTBEAT — Run on scheduled cadence

## 0. GitHub Auth
- Mint installation token: `export GITHUB_TOKEN=$(gh auth token --hostname github.com) && export GH_TOKEN=$GITHUB_TOKEN`
- Token expires in 1hr — mint fresh every heartbeat
- Clone repo if needed: `git clone ${REPO_URL} . 2>/dev/null || true`


## 1. Vulnerability Scan
- Check Trivy/Grype scan results for all container images
- Review npm/nuget dependency audit reports
- Any new CVEs affecting the stack?

## 2. Configuration Audit
- Verify no hard-coded secrets in any repo
- Check ESO ExternalSecret resources are healthy
- Verify Keycloak realm configuration: token lifetimes, MFA
- Audit OpenBao policies: least privilege maintained?

## 3. Network Review
- Istio AuthorizationPolicies: any overly permissive rules?
- NetworkPolicy allowIngressCIDRs: any 0.0.0.0/0 without justification?
- API gateway rate limiting active?
- TLS everywhere: cert-manager, Istio mTLS, database TLS?

## 4. Remediation Tracking
- P0 vulnerabilities: resolved within 24h?
- P1 vulnerabilities: resolved within 72h?
- Report unresolved items to CTO

## 5. Extraction
- Document findings and recommendations
- Update compliance checklist
- File remediation tasks for responsible teams
