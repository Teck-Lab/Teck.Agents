---
name: Teck Conventions
description: Cross-repo naming conventions, patterns, and structural rules for the Teck platform
slug: teck-conventions
schema: agentskills/v1
version: 1.0.0
---

# Teck Conventions

This skill encodes the cross-repo conventions that every Teck agent must follow.

## Naming Rules

| Context | Convention | Example |
|---------|-----------|---------|
| .NET services | kebab-case image names | `basket-api`, `yarp-gateway` |
| Container image tags | `sha-{7-char-hash}` | `sha-412a04c` |
| Kubernetes namespaces | lowercase, hyphens | `teck-cloud-core`, `cnpg-system` |
| TypeScript apps | `@teck/{app-name}` | `@teck/web`, `@teck/web-dashboard` |
| TypeScript packages | `@teck/{package-name}` | `@teck/ui`, `@teck/tsconfig` |
| Terraform modules | kebab-case directory | `cert-manager`, `argocd` |
| Terraform outputs | snake_case | `database_host`, `service_url` |

## Cross-Repo Rules

- Never hard-code image tags in GitOps — Kargo manages them
- Never hard-code environment-specific values — use Kustomize overlays
- Never use `latest` tag in GitOps overlays
- New services must follow the complete cross-repo checklist:
  1. Teck.Cloud: create service projects + migration projects
  2. Teck.GitOps: add overlay dirs under `teck-cloud-core/`
  3. Teck.Terraform: wire database/broker if needed
  4. Teck.Web: add API client generation
- API contracts: OpenAPI specs in Teck.Cloud → codegen in Teck.Web

## Repository Boundaries

| Repo | Owns |
|------|------|
| Teck.Cloud | .NET microservices, business logic, API contracts |
| Teck.GitOps | ArgoCD, Kargo, Kustomize, cluster state |
| Teck.Terraform | OpenTofu, platform tooling provisioning |
| Teck.Web | Next.js, UI components, server actions |
