---
name: Verify Deployment Pipeline
assignee: infrastructure-team-leader
project: teck-gitops
schedule:
  startsAt: '2026-06-17T00:00:00Z'
  timezone: UTC
slug: verify-deployment-pipeline
---


Verify the end-to-end deployment pipeline:
1. Confirm Kargo Warehouse detects new image tags correctly
2. Verify Kargo Stage promotion flow: development → production
3. Check ArgoCD ApplicationSets generate correct application names
4. Validate all Kustomize overlays build without errors
5. Verify sync-wave ordering across all resources
6. Document any gaps for CTO review
