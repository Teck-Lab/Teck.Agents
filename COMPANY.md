---
name: Teck Platform Engineering
description: Agentic software engineering team for the Teck platform — a .NET 10 microservices
  ecosystem with Kubernetes GitOps delivery. Agents plan, build, review, test, and deploy across
  four decoupled repos (Teck.Cloud, Teck.GitOps, Teck.Terraform, Teck.Web).
slug: teck-platform-engineering
schema: agentcompanies/v1
version: 1.0.0
license: MIT
authors:
  - name: TeckLab
tags:
  - paperclip
  - e-commerce
  - dotnet
  - nextjs
  - kubernetes
  - microservices
goals:
  - Ship production-quality .NET microservices through clean architecture patterns
  - Maintain GitOps-driven deployment pipeline (ArgoCD + Kargo + Kustomize) with zero manual image tagging
  - Deliver responsive Next.js 16 UIs with strict TypeScript and Biome
  - Enforce cross-repo naming conventions and API contract alignment
  - Provide systematic code review, testing, and deployment gating across all four repos
---

# Teck Platform Engineering

We build and operate the Teck platform — an e-commerce/marketplace backend with 8+ .NET
microservices, two API gateways (YARP public, admin), a Next.js 16 public storefront and
admin dashboard, and a fully automated GitOps deployment pipeline on K3s.

## Platform Stack

| Layer | Technology |
|-------|-----------|
| Backend | .NET 10, Clean Architecture, Entity Framework Core, xUnit |
| Frontend | Next.js 16 (App Router), TypeScript strict, Bun, Turborepo, Biome, Tailwind CSS |
| Infrastructure | Kubernetes (K3s), OpenTofu, Helm |
| GitOps | ArgoCD (app-of-apps), Kargo (image promotion), Kustomize (overlays) |
| Data | PostgreSQL (CNPG), Redis, RabbitMQ |
| Networking | Istio, kgateway, cert-manager, Cloudflare |
| Auth | Keycloak, OpenBao, External Secrets Operator |

## Repositories

| Repo | Purpose |
|------|---------|
| `Teck.Cloud` | .NET 10 microservices — Basket, Catalog, Customer, Device, Location, Order, Product, Statistic + gateways |
| `Teck.GitOps` | ArgoCD + Kargo + Kustomize — cluster state delivery |
| `Teck.Terraform` | OpenTofu — platform tooling provisioning |
| `Teck.Web` | Next.js 16 — public storefront + admin dashboard |

## Organization

```
CEO ────── Product vision, prioritization
├── CMO ── Market strategy, brand, customer acquisition
├── CFO ── Budget, model spend, pricing, ROI
└── CTO ── Architecture, technical decisions, task routing
    ├── Researcher ── Technical spikes, assigned to squads
    ├── Security Engineer ── Security audits, compliance
    ├── Database Engineer ── Shared across teams
    ├── QA Team Lead ── Quality strategy, deployment gating
    │   ├── Backend QA ── .NET tests, migration verification
    │   ├── Frontend QA ── Component testing, accessibility
    │   └── Infrastructure QA ── Manifest validation, Terraform plan review
    ├── Dev Team 1 ── Full-stack (.NET + Next.js)
    │   ├── Team Lead ── Work assignment, quality
    │   ├── Senior ── Complex features, mentorship
    │   ├── Junior BE ── Scoped .NET tasks (Flash)
    │   └── Junior FE ── Scoped UI tasks (Flash)
    ├── Dev Team 2 ── Full-stack (.NET + Next.js)
    │   ├── Team Lead ── Work assignment, quality
    │   ├── Senior ── Complex features, mentorship
    │   ├── Junior BE ── Scoped .NET tasks (Flash)
    │   └── Junior FE ── Scoped UI tasks (Flash)
    └── Infrastructure Team ── GitOps, Terraform, K3s
        ├── Team Lead
        ├── Senior Engineers (2) ── Pipelines, modules
        └── Junior Engineers (4) ── Pattern-following (Flash)
```

## Projects

| Project | Repo |
|---------|------|
| [Teck.Cloud](projects/teck-cloud/PROJECT.md) | Backend microservices |
| [Teck.GitOps](projects/teck-gitops/PROJECT.md) | Cluster state delivery |
| [Teck.Terraform](projects/teck-terraform/PROJECT.md) | Platform provisioning |
| [Teck.Web](projects/teck-web/PROJECT.md) | Frontend storefront + dashboard |

## Skills

## Skills

| Skill | Purpose |
|-------|---------|
| `teck-conventions` | Cross-repo naming, patterns, structural rules |
| `teck-architecture` | Architecture review — boundaries, decomposition, integration |
| `teck-code-review` | Systematic code review checklist across all repos |
| `teck-deployment` | Deployment verification, smoke tests, rollback procedures |

## Model Strategy

Junior engineers are designed for cost-efficient models (Deepseek v4 Flash). Their
tasks are tightly scoped with explicit patterns to follow — single file, single service,
copy-paste from existing code. Senior engineers handle architecture, new patterns,
and cross-cutting changes, and should use full-capability models.
