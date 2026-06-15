---
name: Teck.GitOps
description: ArgoCD + Kargo + Kustomize — cluster state delivery. GitOps delivery layer for the Teck platform using app-of-apps pattern.
slug: teck-gitops
owner: cto
homepage: https://github.com/Teck-Lab/Teck.GitOps
metadata:
  sources:
    - kind: github-dir
      repo: Teck-Lab/Teck.GitOps
      path: /
  stack:
    - ArgoCD
    - Kargo
    - Kustomize
    - Kubernetes (K3s)
    - Istio
---

# Teck.GitOps

GitOps delivery layer for the Teck platform.

## Structure

```
bootstrap/          — cluster bootstrap chain
projects/           — AppProject + ApplicationSet definitions
apps/
  development/      — development stage overlays
  production/       — production stage overlays
  in-cluster/       — cluster-local tooling
cluster-resources/  — raw Kubernetes resources
essentials/         — platform infrastructure
```

## Pipeline

```
CI builds Docker image → pushes sha-{hash} tag
  → Kargo Warehouse detects → promotes Freight
  → Kargo Stage promotes to development (auto) → production (manual)
  → ArgoCD syncs overlay changes to cluster
```

## Conventions

- Never hard-code image tags — Kargo manages them
- Never hard-code environment values — use Kustomize overlays
- Image policy regex: `^sha-[a-f0-9]{7}$`
- Sync-wave annotations required on all resources
- Namespaces: `teck-cloud-core`, `auth`, `monitoring`, `network`
