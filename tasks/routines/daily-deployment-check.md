---
name: Daily Deployment Health Check
assignee: qa-team-lead
recurring: true
schedule:
  cron: "0 7 * * *"
  timezone: UTC
---
Verify deployment pipeline and cluster health:
1. Check ArgoCD sync status: all applications healthy?
2. Kargo promotions: any stuck in development or production?
3. Run smoke tests on development environment
4. Verify service health endpoints respond
5. Check monitoring for new alerts in last 24h
6. Report deployment readiness to CTO
