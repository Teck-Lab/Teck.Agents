# PROJECT-INVENTORY.md

## Product Identity
- **Company**: Teck Platform Engineering
- **Product**: Teck — e-commerce/marketplace platform
- **Correct spelling**: "Teck" (never "Teck.", "TeckLab", "teck")

## What Exists
- 8+ .NET microservices: Basket, Catalog, Customer, Device, Location, Order, Product, Statistic
- Image Generator service
- 3 API gateways: YARP (public), Admin, Aggregate
- Next.js 16 public storefront + admin dashboard
- Full GitOps pipeline: ArgoCD + Kargo + Kustomize
- Platform tooling via OpenTofu: K3s, CNPG, Redis, RabbitMQ, Istio, cert-manager

## Directory Ownership
| Directory | Owner | Notes |
|-----------|-------|-------|
| `repos/Teck.Cloud/` | Dev Teams | .NET microservices |
| `repos/Teck.Web/` | Dev Teams | Next.js frontend |
| `repos/Teck.GitOps/` | Infra Team | GitOps delivery |
| `repos/Teck.Terraform/` | Infra Team | Platform provisioning |
| `repos/Teck.Images/` | Infra Team | Container builds |

## Current Phase
Platform is live in development. Production deployment in progress. Active development across all repos.

## Infrastructure
- **Hosting**: Hetzner Cloud (K3s)
- **CI/CD**: GitHub Actions → Kargo → ArgoCD
- **Monitoring**: Victoria Metrics + Grafana
- **Domains**: tecklab.dk, teck.se, teck.dk
- **DNS**: Cloudflare + external-dns

## Key Contacts (outside Paperclip)
- (None — all work done by Paperclip agents)

---

*Check this file before starting any new work to avoid recreating existing deliverables.*
