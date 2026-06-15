---
name: Teck Deployment
description: Deployment verification skill for the Teck platform — validates Kargo promotions, ArgoCD syncs, and smoke tests across all environments
slug: teck-deployment
schema: agentskills/v1
version: 1.0.0
---

# Teck Deployment Verification

This skill guides deployment verification for the Teck platform.

## Pre-Deployment Checklist (Development)

Before promoting to development:

- [ ] Kustomize overlays build without errors: `kustomize build apps/development/teck-cloud/teck-cloud-core/{service}`
- [ ] Kubernetes manifests validate: `kustomize build | kubeconform`
- [ ] Image tag matches CI output (`sha-{7-char-hash}` format)
- [ ] Kargo Warehouse subscription covers the new image
- [ ] ArgoCD ApplicationSet templates generate correct Application names
- [ ] Sync-wave ordering is correct

## Post-Development Deployment

After ArgoCD syncs development:

- [ ] ArgoCD reports Healthy status for all synced applications
- [ ] Pods are Running and Ready
- [ ] Service endpoints respond: `GET /health`
- [ ] Database migrations applied (check CNPG logs)
- [ ] Istio routes working (check kgateway HTTPRoute status)
- [ ] Smoke test: basic CRUD operations on changed services
- [ ] Cross-service smoke test: order flow (Basket → Order), catalog browsing

## Production Promotion Gate

Before approving Kargo production promotion:

- [ ] All development checks passed
- [ ] QA Team Leader has approved
- [ ] No P0 or P1 bugs open for affected services
- [ ] Database migration has been verified on development
- [ ] Rollback plan documented (previous image tag + ArgoCD rollback)

## Post-Production Verification

After production deployment:

- [ ] ArgoCD reports Healthy
- [ ] Health endpoints respond
- [ ] Smoke tests pass
- [ ] Error rates stable (check monitoring)
- [ ] No new alerts triggered

## Rollback Procedure

If deployment fails:
1. Revert the Kustomize image tag to the last known good `sha-{hash}`
2. Push the revert commit
3. ArgoCD auto-syncs to the reverted state
4. Verify health
5. Investigate root cause before re-promoting
