---
name: QA Baseline Test Suite
assignee: qa-team-lead
project: teck-cloud
schedule:
  startsAt: '2026-06-17T00:00:00Z'
  timezone: UTC
slug: qa-baseline
---



Establish baseline test coverage across all repos:
1. Backend: verify integration test suites run for all services
2. Frontend: verify build/lint/typecheck pass for all apps
3. Infrastructure: verify kustomize build + kubeconform for all overlays
4. Cross-service: verify order flow, catalog browsing, auth flows
5. Document test coverage gaps and prioritize with CTO
