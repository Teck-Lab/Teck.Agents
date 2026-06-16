---
name: Weekly Architecture Review
assignee: cto
recurring: true
schedule:
  cron: "0 9 * * 1"
  timezone: UTC
---
Review architecture across all repos:
1. Check clean architecture boundaries in Teck.Cloud (no Domain→Infra leaks)
2. Verify cross-repo naming conventions (kebab-case, sha tags)
3. Audit new services for cross-repo checklist compliance
4. Review API contract changes from OpenAPI specs
5. Check GitOps pipeline health (ArgoCD sync, Kargo promotions)
6. Document architectural decisions and flag tech debt
