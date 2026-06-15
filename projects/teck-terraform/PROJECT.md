---
name: Teck.Terraform
description: OpenTofu — platform tooling provisioning. Helm-based infrastructure management for K3s cluster.
slug: teck-terraform
owner: cto
homepage: https://github.com/Teck-Lab/Teck.Terraform
metadata:
  sources:
    - kind: github-dir
      repo: Teck-Lab/Teck.Terraform
      path: /
  stack:
    - OpenTofu
    - Helm
    - Kubernetes (K3s)
    - Hetzner Cloud
---

# Teck.Terraform

Platform tooling provisioning for the Teck platform.

## Structure

```
modules/   — one sub-folder per tool (argocd, cert-manager, etc.)
apps/      — root module wiring all modules together
providers/ — cloud provider configuration (Hetzner)
```

## Managed Tools

| Tool | Module | Purpose |
|------|--------|---------|
| ArgoCD | `argocd` | GitOps controller |
| cert-manager | `cert-manager` | TLS certificate management |
| CNPG | `cnpg` | PostgreSQL operator |
| External Secrets | `eso` | Secrets from Vault |
| RabbitMQ | `rabbitmq-operator` | Message broker |
| Redis | `redis-shared` | Cache and session store |

## Conventions

- Use `tofu` CLI — not `terraform`
- All infrastructure via `helm_release` resources
- Module structure: `modules/{tool}/{main,variables,outputs,versions}.tf`
- Chart versions pinned as variables with defaults
- Sensitive outputs marked `sensitive = true`
- Module dependencies via `depends_on` in `apps/main.tf`
