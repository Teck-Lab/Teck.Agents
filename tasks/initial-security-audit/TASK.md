---
name: Initial Security Audit
assignee: security-engineer
project: teck-cloud
---

Run comprehensive security audit across all repos:
1. Scan Teck.Cloud: OWASP top 10, EF Core injection, hard-coded secrets
2. Scan Teck.Web: CSRF, XSS, server action validation gaps
3. Scan Teck.GitOps: exposed secrets in overlays, missing sync-wave annotations
4. Scan Teck.Terraform: overly permissive IAM, missing sensitive outputs
5. Report findings with CVSS scores and remediation priorities to CTO
