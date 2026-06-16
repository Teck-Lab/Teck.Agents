---
name: Daily Security Scan
assignee: security-engineer
recurring: true
schedule:
  cron: "0 8 * * *"
  timezone: UTC
---
Run comprehensive security scan across all repos:
1. Check Trivy/Grype scan results for container images
2. Audit npm/nuget dependency reports for CVEs
3. Verify no hard-coded secrets in any repo
4. Check ESO ExternalSecret resources are healthy
5. Review Istio AuthorizationPolicies for new gaps
6. Report findings with severity to CTO
