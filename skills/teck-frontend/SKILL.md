---
name: Teck Frontend
description: Next.js 16, TypeScript strict, Bun, Turborepo, Biome, Tailwind CSS conventions for the Teck platform
slug: teck-frontend
schema: agentskills/v1
version: 1.0.0
---

# Teck Frontend Conventions

This skill encodes frontend-specific patterns for the Teck platform.

## Tech Stack

| Tool | Version | Purpose |
|------|---------|---------|
| Next.js | 16 (App Router) | React framework |
| TypeScript | strict mode | Type safety |
| Bun | latest | Package manager, runtime |
| TurboRepo | latest | Monorepo task pipeline |
| Biome | latest | Formatting + linting |
| Tailwind CSS | v4 | Styling via `@teck/tailwind-config` |
| next-safe-action | latest | Server actions with zod validation |

## Package Naming

- Apps: `@teck/{app-name}` — `@teck/web`, `@teck/web-dashboard`, `@teck/storybook`, `@teck/docs`
- Packages: `@teck/{package-name}` — `@teck/ui`, `@teck/tailwind-config`, `@teck/tsconfig`

## Component Rules

- **Server components by default** — add `"use client"` only when interactivity required
- **Use existing `@teck/ui` components** before creating new ones
- **Never import server-only code** into client components
- **Responsive design** — test all breakpoints
- **Accessibility** — keyboard navigation, screen reader, color contrast

## Server Actions

- All server actions via `next-safe-action` with `zod` schemas
- API client generated from backend OpenAPI specs
- Proper error handling: loading, error, empty states for all data-fetching components

## Tooling

- **Bun** for package management — never `npm` or `yarn`
- **Biome** for formatting and linting — never ESLint or Prettier
- **TypeScript strict** — no `any` types, no `@ts-ignore`
- Run tasks via Turborepo: `bun run build`, `bun run lint`, `bun run typecheck`

## Quality Gates

- `bun run build` passes
- `bun run lint` passes (Biome)
- `bun run typecheck` passes (TypeScript strict)
- No `any` types or type assertion bypasses
- Component tests for critical interaction paths
- Visual regression notes for UI changes
