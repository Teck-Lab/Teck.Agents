---
name: QA Team
slug: qa
description: Quality assurance, testing, and deployment gating for the Teck platform.
schema: agentcompanies/v1
version: 1.0.0
includes:
  - qa-team-lead
  - backend-qa
  - frontend-qa
  - infrastructure-qa
---

# QA Team

Owns quality strategy, test planning, and deployment gating across all four repos.

## Structure
- QA Team Lead → Backend QA + Frontend QA + Infrastructure QA

## Responsibilities
- Backend QA: .NET integration tests, EF Core migration verification, API contract testing
- Frontend QA: Component rendering, responsive layout, accessibility audits, Biome/typecheck validation
- Infrastructure QA: Manifest validation, Kustomize build verification, Terraform plan review
- Cross-service integration testing
- Production promotion gating
