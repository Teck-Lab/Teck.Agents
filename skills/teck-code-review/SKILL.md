---
name: Teck Code Review
description: Code review checklist for the Teck platform — validates against conventions, architecture rules, and quality gates across all four repos
slug: teck-code-review
schema: agentskills/v1
version: 1.0.0
---

# Teck Code Review

This skill provides a systematic code review checklist for the Teck platform.

## Review by Repo

### Teck.Cloud (.NET)

- [ ] Clean architecture boundaries intact? (no Domain→Infrastructure, no API→Domain)
- [ ] No type error suppression (`as any`, `@ts-ignore`, `@ts-expect-error`)? **HARD BLOCK**
- [ ] Capability-first folders? (`{Capability}/Features/{UseCase}/V1`)
- [ ] Request validators present for all endpoints?
- [ ] Database migrations included for all three providers?
- [ ] Tests follow xUnit conventions in correct test project?
- [ ] No unrelated refactoring in feature branch?
- [ ] Service registered in Aspire AppHost if new?

### Teck.Web (TypeScript/Next.js)

- [ ] Build passes? (`bun run build`)
- [ ] Lint passes? (`bun run lint` via Biome)
- [ ] Typecheck passes? (`bun run typecheck`)
- [ ] Server components vs client components correctly chosen?
- [ ] Server actions use `next-safe-action` with `zod` schemas?
- [ ] No `any` types bypassing strict mode?
- [ ] Shared components from `@teck/ui` used where applicable?
- [ ] No hard-coded API URLs — using generated client?

### Teck.GitOps (YAML/Kustomize)

- [ ] No hard-coded image tags? **HARD BLOCK**
- [ ] No environment-specific values outside overlays?
- [ ] Valid Kubernetes manifests or Kustomize resources?
- [ ] Correct `argocd.argoproj.io/sync-wave` annotations?
- [ ] Correct namespace and naming conventions?
- [ ] Kustomize builds without errors? (`kustomize build`)

### Teck.Terraform (OpenTofu)

- [ ] Helm chart versions pinned with variables?
- [ ] Sensitive outputs marked `sensitive = true`?
- [ ] Module dependencies via `depends_on` in `apps/main.tf`?
- [ ] No hard-coded environment values?
- [ ] `tofu plan` runs clean?

## Cross-Repo Checks

- [ ] New service follows the complete cross-repo checklist?
- [ ] API contracts match between Teck.Cloud (OpenAPI) and Teck.Web (client)?
- [ ] Container image tags follow `^sha-[a-f0-9]{7}$` pattern in GitOps?
- [ ] Naming consistent across repos (kebab-case services, matching names)?

## Severity

- **Blocking**: Violates a hard block rule. Must fix before merge.
- **Advisory**: Improvement suggestion. Can merge, should track.
- **Architectural**: Fundamental design concern. Escalate to CTO.
