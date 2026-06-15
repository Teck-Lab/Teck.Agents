---
name: Teck Architecture
description: Architecture review skill for the Teck platform — validates clean architecture boundaries, service decomposition, and cross-service integration
slug: teck-architecture
schema: agentskills/v1
version: 1.0.0
---

# Teck Architecture Review

This skill guides architectural decisions and reviews for the Teck platform.

## Clean Architecture Boundaries (Teck.Cloud)

Architecture layers must respect their boundaries:

- **Domain**: Entities, value objects, domain events, repository interfaces. No dependencies on Application, Infrastructure, or API layers.
- **Application**: Use cases, commands/queries, validators, DTOs. Depends on Domain only. No Infrastructure or API dependencies.
- **Infrastructure**: EF Core implementations, external service clients, persistence. Depends on Application (for interfaces) and Domain.
- **API**: Endpoint classes, controllers, minimal API mappings. Transport-thin — no business logic. Depends on Application.

## Project Structure

```
src/services/{service}/
├── {Service}.Domain/
├── {Service}.Application/
│   ├── {Capability}/Features/{UseCase}/V1/
│   ├── {Capability}/Responses/
│   └── {Capability}/EventHandlers/DomainEvents/
├── {Service}.Infrastructure/
│   └── {Service}.Infrastructure.Migrations.{Provider}/
└── {Service}.Api/
```

## Service Design Principles

- Each service owns its data — no direct cross-service database access
- Services communicate via HTTP (REST/OpenAPI), gRPC, or message bus
- API gateways (YARP public, admin) handle routing — services don't know about gateways
- New services must have all three migration providers (MySql, PostgreSQL, SqlServer)

## GitOps Architecture (Teck.GitOps)

- App-of-apps pattern: `bootstrap/root.yaml` → watches `projects/` → generates Applications
- Kargo pipeline: Warehouse (detects tags) → Freight (snapshot) → Stage (promotes)
- Sync-wave ordering: -2 (projects), 0 (ApplicationSets), 1 (essentials), 2 (workloads)
- Environments: development (auto-promote), production (manual approval)

## Frontend Architecture (Teck.Web)

- Server components by default, `"use client"` only when interactivity required
- Server actions via `next-safe-action` with `zod` validation
- API client generated from OpenAPI specs, consumed by server actions
- Shared components in `@teck/ui` package

## Infrastructure Architecture (Teck.Terraform)

- All infrastructure via Helm releases with `helm_release` resource
- Modules: `modules/{tool}/{main,variables,outputs,versions}.tf`
- Chart versions pinned with variables, not hard-coded
- Module dependencies declared via `depends_on` in `apps/main.tf`
