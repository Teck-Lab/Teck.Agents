# Teck Platform Goals — Paperclip
# Goal lifecycle: proposed → planned → active → completed → archived
# Create via Paperclip UI or API. Parent goals first, note ID, then sub-goals with parentId.

# ============================================================
# GOAL 1: Ship Production-Ready Platform (CEO)
# ============================================================
title: Ship Production-Ready Platform
type: company
status: active
owner: ceo
description: Deploy the Teck platform to production with core e-commerce flows working end-to-end across all four repos.

Sub-goals:
  - title: Deliver Basket → Order → Catalog flow
    type: company
    status: active
    owner: ceo
    description: Complete cross-service integration testing for the core ordering flow. Basket API creates orders, Catalog API serves products, Order API processes fulfillment. All integration tests passing.

  - title: Deploy to production via Kargo
    type: company
    status: active
    owner: ceo
    description: Achieve zero-downtime production deployment using Kargo image promotion. No manual image tags. ArgoCD syncs healthy at all stages.

  - title: Achieve 95% test coverage on .NET services
    type: company
    status: active
    owner: ceo
    description: All 8 microservices and 3 gateways must have unit + integration tests covering 95% of code paths. Tracked per service.

  - title: Onboard first external merchant
    type: company
    status: active
    owner: ceo
    description: Ship the public storefront, allow a real merchant to list products and receive orders. Validate the full customer journey.

# ============================================================
# GOAL 2: Achieve Cost Efficiency (CFO)
# ============================================================
title: Achieve Cost Efficiency
type: company
status: active
owner: cfo
description: Keep model spend under control while maintaining quality. Juniors on Flash, seniors on appropriate tiers, no wasted tokens.

Sub-goals:
  - title: 80%+ of agent tasks on Flash tier
    type: company
    status: active
    owner: cfo
    description: Juniors, QA, and Researcher must stay on v4-flash. Flag any Junior burning k2p7 or v4-pro immediately.

  - title: Reduce model spend per feature by 25%
    type: company
    status: active
    owner: cfo
    description: Quarter-over-quarter reduction in average token cost per completed feature. Track via CFO weekly spend review.

  - title: Eliminate stale dependency PRs
    type: company
    status: active
    owner: cfo
    description: Auto-archive Dependabot PRs older than 30 days. Keep the PR queue actionable.

  - title: Weekly spend reporting
    type: company
    status: active
    owner: cfo
    description: CFO produces a per-squad spend report every Friday. Published to the board. CEO reviews.

# ============================================================
# GOAL 3: Enforce Security & Compliance (Security Engineer)
# ============================================================
title: Enforce Security title: Enforce Security & Compliance Compliance
type: company
status: active
owner: security-engineer
description: Zero critical findings, zero hard-coded secrets, zero expired certificates across all four repos.

Sub-goals:
  - title: Pass OWASP Top 10 audit
    type: company
    status: active
    owner: cfo
    description: Complete security audit of all .NET services. No critical or high findings. Remediate all medium findings within 7 days.

  - title: Zero hard-coded secrets
    type: company
    status: active
    owner: cfo
    description: Verify no API keys, passwords, or tokens in any repo. All secrets via External Secrets Operator from Vault.

  - title: Cert-manager auto-renewal
    type: company
    status: active
    owner: cfo
    description: All TLS certificates renew automatically via cert-manager. Zero expired certificates in production.

  - title: Complete initial security audit
    type: company
    status: active
    owner: cfo
    description: Security Engineer audits all 4 repos within first week. Report findings to CTO with CVSS scores and remediation priorities.

# ============================================================
# GOAL 4: Deliver Core Microservices (Dev Teams)
# ============================================================
title: Deliver Core Teck.Cloud Microservices
project: teck-cloud
type: team
status: active
owner: dev-team-1-tl
description: Ship the foundational backend services with clean architecture, full test coverage, and all three database providers.

Sub-goals:
  - title: Ship Basket API
    type: team
    status: active
    owner: dev-team-1-tl
    description: Full CRUD operations with Redis session caching. Integration tests passing on all three providers.

  - title: Ship Catalog API
    type: team
    status: active
    owner: dev-team-1-tl
    description: Product search, filtering, and category browsing. RabbitMQ events for inventory updates.

  - title: Ship Order API
    type: team
    status: active
    owner: dev-team-1-tl
    description: Order creation, status tracking, and RabbitMQ event publishing. Cross-service integration with Basket and Catalog.

  - title: Migration coverage
    type: team
    status: active
    owner: dev-team-1-tl
    description: All three database providers (MySql, PostgreSQL, SqlServer) have passing migrations for every service.

# ============================================================
# GOAL 5: Deliver Storefront & Dashboard (Dev Teams)
# ============================================================
title: Deliver Teck.Web Frontend
project: teck-web
type: team
status: active
owner: dev-team-2-tl
description: Ship the public storefront and admin dashboard with production-quality UI, accessibility, and performance.

Sub-goals:
  - title: Ship public storefront
    type: team
    status: active
    owner: dev-team-2-tl
    description: Product browsing, cart, checkout flow. Responsive design. Lighthouse score >90.

  - title: Ship admin dashboard
    type: team
    status: active
    owner: dev-team-2-tl
    description: Order management, product CRUD, customer management. Built with @teck/ui shared components.

  - title: Biome + TypeScript strict compliance
    type: team
    status: active
    owner: dev-team-2-tl
    description: All apps pass `bun run build`, `bun run lint`, `bun run typecheck` with zero errors.

  - title: Accessibility audit
    type: team
    status: active
    owner: dev-team-2-tl
    description: Frontend QA completes accessibility audit. Keyboard navigation, screen reader, color contrast all passing.

# ============================================================
# GOAL 6: Maintain Platform Reliability (Infra Team)
# ============================================================
title: Maintain Platform Reliability
project: teck-gitops
type: team
status: active
owner: infrastructure-team-leader
description: Keep the GitOps pipeline healthy, the cluster stable, and the deployment process automated and reliable.

Sub-goals:
  - title: ArgoCD sync health
    type: team
    status: active
    owner: infrastructure-team-leader
    description: All ArgoCD applications report Healthy status. Zero out-of-sync resources in production.

  - title: Kargo promotion pipeline
    type: team
    status: active
    owner: infrastructure-team-leader
    description: Zero failed Kargo promotions. Images flow from development to production without manual intervention.

  - title: Database backup verification
    type: team
    status: active
    owner: infrastructure-team-leader
    description: Weekly verification that CNPG backups are restorable. Documented and tested.

  - title: Infrastructure as Code validation
    type: team
    status: active
    owner: infrastructure-team-leader
    description: All Kustomize overlays build clean. All Terraform plans are clean. No drift in production.

# ============================================================
# GOAL 7: Agent Onboarding (QA Team Lead + CTO)
# ============================================================
title: Onboard All Agents
description: Every agent configured, tested, and running their initial tasks. Full heartbeat coverage across the org chart.

Sub-goals:
  - title: Import and configure all 23 agents
    type: team
    status: active
    owner: infrastructure-team-leader
    description: All agents imported from Teck.Agents with correct adapters, models, and skills. Verified by CTO.

  - title: Complete onboarding tasks
    type: team
    status: active
    owner: infrastructure-team-leader
    description: All 5 onboarding tasks completed: backend audit, frontend audit, security audit, deployment verification, QA baseline.

  - title: Heartbeat coverage
    type: team
    status: active
    owner: infrastructure-team-leader
    description: All strategic roles (CEO, CTO, CMO, CFO, QA TL, Security Engineer) have working heartbeats. Dev Team leads have heartbeat + spec creation flow.

  - title: Daily routines running
    type: team
    status: active
    owner: infrastructure-team-leader
    description: Daily Security Scan, Daily Deployment Health Check, Weekly Architecture Review, Weekly Spend Review, Monday Market Brief all active and running.


## Import via API

```bash
PAPERCLIP_API_URL=http://localhost:3100
COMPANY_ID=<your-company-id>

# Create parent goals
curl -X POST "$PAPERCLIP_API_URL/api/companies/$COMPANY_ID/goals" \
  -H "Content-Type: application/json" \
  -d '{"title":"Ship Production-Ready Platform","description":"Deploy to production with core flows","type":"company","status":"planned"}'

# Create sub-goal (note parentId from response)
curl -X POST "$PAPERCLIP_API_URL/api/companies/$COMPANY_ID/goals" \
  -H "Content-Type: application/json" \
  -d '{"title":"Deliver Basket → Order flow","description":"Cross-service integration testing","type":"task","status":"planned","parentId":"<goal-id>"}'
```

Or use the Paperclip UI: Company Settings → Goals → New Goal


# ============================================================
# GOAL 8: Core Authentication & User Management (Backend — teck-cloud)
# ============================================================
title: Core Authentication & User Management
project: teck-cloud
type: team
status: planned
owner: dev-team-1-tl
description: Keycloak-based auth with user registration, login, role management, and secure API access across all services.

Sub-goals:
  - title: Keycloak realm configuration
    type: task
    status: planned
    owner: dev-team-1-tl
    description: Configure Keycloak realm with clients, roles, and OIDC flows for all services.

  - title: User registration & login API
    type: task
    status: planned
    owner: dev-team-1-tl
    description: Customer API endpoints for signup, login, password reset via Keycloak.

  - title: Role-based access control
    type: task
    status: planned
    owner: dev-team-1-tl
    description: Admin, merchant, and customer roles enforced at API gateway level via YARP + Keycloak.

  - title: Token refresh & session management
    type: task
    status: planned
    owner: dev-team-1-tl
    description: Automatic token refresh, session expiry, and secure cookie handling for web client.


# ============================================================
# GOAL 9: Product Catalog & Search (Backend — teck-cloud)
# ============================================================
title: Product Catalog & Search
project: teck-cloud
type: team
status: planned
owner: dev-team-1-tl
description: Full product management with categories, attributes, variants, and Elasticsearch-powered search.

Sub-goals:
  - title: Product CRUD API
    type: task
    status: planned
    owner: dev-team-1-tl
    description: Product API with create, read, update, delete, and soft-delete. Image and variant support.

  - title: Category hierarchy
    type: task
    status: planned
    owner: dev-team-1-tl
    description: Nested category tree with parent-child relationships and SEO-friendly slugs.

  - title: Elasticsearch integration
    type: task
    status: planned
    owner: dev-team-1-tl
    description: Full-text search with faceted filtering, autocomplete, and relevance scoring. Synced from Catalog API via RabbitMQ.

  - title: Product variants & SKUs
    type: task
    status: planned
    owner: dev-team-1-tl
    description: Size, color, and custom attribute variants with unique SKU generation and inventory tracking.


# ============================================================
# GOAL 10: Merchant Dashboard & Product Management (Frontend — teck-web)
# ============================================================
title: Merchant Dashboard & Product Management
project: teck-web
type: team
status: planned
owner: dev-team-2-tl
description: Admin dashboard for merchants to manage products, view orders, and track analytics.

Sub-goals:
  - title: Product management UI
    type: task
    status: planned
    owner: dev-team-2-tl
    description: Create, edit, and manage products with image upload, variant configuration, and pricing.

  - title: Order management dashboard
    type: task
    status: planned
    owner: dev-team-2-tl
    description: View, filter, and update orders. Status transitions: pending → confirmed → shipped → delivered.

  - title: Analytics overview
    type: task
    status: planned
    owner: dev-team-2-tl
    description: Revenue charts, order volume, top products, and customer metrics dashboard for merchants.

  - title: Inventory management
    type: task
    status: planned
    owner: dev-team-2-tl
    description: Stock level monitoring, low-stock alerts, and bulk inventory updates.


# ============================================================
# GOAL 11: Payment Processing (Post-MVP — teck-cloud + teck-terraform)
# ============================================================
title: Payment Processing
project: teck-cloud
type: company
status: proposed
owner: cto
description: Multi-provider payment integration supporting cards, wallets, and local payment methods.

Sub-goals:
  - title: Stripe integration
    type: task
    status: proposed
    owner: dev-team-1-tl
    description: Stripe Payment Intents API with webhook handling for async payment confirmation.

  - title: PayPal integration
    type: task
    status: proposed
    owner: dev-team-1-tl
    description: PayPal Smart Buttons with order capture and refund support.

  - title: Payment webhook infrastructure
    type: task
    status: proposed
    owner: infrastructure-team-leader
    description: Reliable webhook receiver with idempotency, retry, and reconciliation for all payment providers.

  - title: Refund & dispute handling
    type: task
    status: proposed
    owner: dev-team-1-tl
    description: Automated refund processing and chargeback dispute workflow in Order API.


# ============================================================
# GOAL 12: Shipping & Logistics (Post-MVP — teck-cloud)
# ============================================================
title: Shipping & Logistics
project: teck-cloud
type: company
status: proposed
owner: cto
description: Carrier integration, real-time rates, label generation, and order tracking.

Sub-goals:
  - title: Multi-carrier rate calculation
    type: task
    status: proposed
    owner: dev-team-1-tl
    description: Real-time shipping rates from multiple carriers at checkout.

  - title: Label generation
    type: task
    status: proposed
    owner: dev-team-1-tl
    description: Automated shipping label generation and printing via carrier APIs.

  - title: Order tracking
    type: task
    status: proposed
    owner: dev-team-2-tl
    description: Customer-facing tracking page with carrier integration and status updates.


# ============================================================
# GOAL 13: Media & Asset Management (Post-MVP — teck-cloud + teck-web)
# ============================================================
title: Media & Asset Management
project: teck-web
type: company
status: proposed
owner: cto
description: Image processing, CDN delivery, video support, and digital asset organization.

Sub-goals:
  - title: Image processing pipeline
    type: task
    status: proposed
    owner: dev-team-1-tl
    description: Automatic image resizing, format conversion (WebP), and optimization via Image Generator service.

  - title: CDN integration
    type: task
    status: proposed
    owner: infrastructure-team-leader
    description: Cloudflare R2 or S3-compatible storage with CDN caching for all media assets.

  - title: Product image gallery
    type: task
    status: proposed
    owner: dev-team-2-tl
    description: Multi-image upload, reordering, zoom, and thumbnail generation in merchant dashboard.

  - title: Video product demos
    type: task
    status: proposed
    owner: dev-team-2-tl
    description: Embedded video support for product pages with lazy loading and responsive embeds.


# ============================================================
# GOAL 14: Third-Party Integrations & API Platform (teck-cloud)
# ============================================================
title: Third-Party Integrations & API Platform
project: teck-cloud
type: company
status: proposed
owner: cto
description: Public API, webhooks, and integration marketplace for third-party developers and ERP systems.

Sub-goals:
  - title: Public REST API
    type: task
    status: proposed
    owner: dev-team-1-tl
    description: Developer-facing REST API with OpenAPI spec, rate limiting, and API key management.

  - title: Webhook system
    type: task
    status: proposed
    owner: dev-team-1-tl
    description: Configurable webhooks for order events, product updates, and customer actions with retry and delivery logs.

  - title: ERP integration
    type: task
    status: proposed
    owner: dev-team-1-tl
    description: Bi-directional sync with ERP systems for inventory, orders, and financial data.

  - title: OAuth for third-party apps
    type: task
    status: proposed
    owner: dev-team-1-tl
    description: OAuth 2.0 provider for third-party applications to access merchant data with granular scopes.
