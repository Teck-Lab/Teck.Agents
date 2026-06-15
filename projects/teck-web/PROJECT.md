---
name: Teck.Web
description: Next.js 16 App Router + TypeScript + Bun + TurboRepo. Public storefront and admin dashboard for the Teck platform.
slug: teck-web
owner: cto
homepage: https://github.com/Teck-Lab/Teck.Web
metadata:
  sources:
    - kind: github-dir
      repo: Teck-Lab/Teck.Web
      path: /
  stack:
    - Next.js 16
    - TypeScript (strict)
    - Bun
    - Turborepo
    - Biome
    - Tailwind CSS
    - next-safe-action
    - zod
---

# Teck.Web

Frontend monorepo for the Teck platform.

## Apps

| App | Package | Description |
|-----|---------|-------------|
| Web | `@teck/web` | Public-facing storefront |
| Web Dashboard | `@teck/web-dashboard` | Admin dashboard |
| Storybook | `@teck/storybook` | Component development |
| Docs | `@teck/docs` | Documentation site |

## Packages

| Package | Description |
|---------|-------------|
| `@teck/ui` | Shared React component library |
| `@teck/tailwind-config` | Shared Tailwind CSS configuration |
| `@teck/tsconfig` | Shared TypeScript configurations |

## Conventions

- **Bun** for package management — never npm or yarn
- **Biome** for formatting and linting — never ESLint or Prettier
- **TypeScript strict** everywhere — no `any` types
- **Server components** by default — `"use client"` only when needed
- **next-safe-action** with **zod** for all server actions
- **API client** generated from OpenAPI specs
