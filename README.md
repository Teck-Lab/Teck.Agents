# Teck.Agents

Paperclip company package for the Teck platform engineering team. Pre-configured
AI agents organized in three squads (Backend, Frontend, Infrastructure) with
embedded QA. Researcher reports to CTO and is assigned to squads as needed.
Juniors use Deepseek v4 Flash for cost-efficient scoped tasks.

## Organization

```
CEO
├── CMO ← Market, brand, growth (gpt-5.5)
├── CFO ← Budget, model spend, pricing (v4-pro)
└── CTO ← Architecture, engineering, security
    ├── Security Engineer ← Security audits, compliance
    ├── Researcher ← Technical spikes, assigned to squads
    ├── Backend Squad (Teck.Cloud)
    │   ├── Backend Team Leader
    │   ├── Senior Backend Engineer
    │   ├── Junior Backend Engineer  ← Flash
    │   ├── Database Engineer
    │   └── QA Engineer
    ├── Frontend Squad (Teck.Web)
    │   ├── Frontend Team Leader
    │   ├── Senior Frontend Engineer
    │   ├── Junior Frontend Engineer  ← Flash
    │   └── QA Engineer
    └── Infrastructure Squad (Teck.GitOps + Teck.Terraform)
        ├── Infrastructure Team Leader
        ├── Senior Infrastructure Engineer
        ├── Junior Infrastructure Engineer  ← Flash
        └── QA Engineer
```


## Agents

| Agent | Domain | Reports To |
|-------|--------|-----------|
| [CEO](agents/ceo/AGENTS.md) | Product vision | — |
| [CTO](agents/cto/AGENTS.md) | Architecture, routing | CEO |
| [Researcher](agents/researcher/AGENTS.md) | Technical spikes (all squads) | CTO |
| [Security Engineer](agents/security-engineer/AGENTS.md) | Security audits, compliance (all squads) | CTO |
| [Backend TL](agents/backend-team-leader/AGENTS.md) | .NET microservices | CTO |
| [Senior BE](agents/senior-backend-engineer/AGENTS.md) | Complex services | Backend TL |
| [Junior BE](agents/junior-backend-engineer/AGENTS.md) | Scoped tasks (Flash) | Senior BE |
| [Database Engineer](agents/database-engineer/AGENTS.md) | Schema, migrations, queries | Backend TL |
| [Backend QA](agents/backend-qa/AGENTS.md) | Squad testing | Backend TL |
| [Frontend TL](agents/frontend-team-leader/AGENTS.md) | Next.js, UI | CTO |
| [Senior FE](agents/senior-frontend-engineer/AGENTS.md) | Complex pages | Frontend TL |
| [Junior FE](agents/junior-frontend-engineer/AGENTS.md) | Scoped tasks (Flash) | Senior FE |
| [Frontend QA](agents/frontend-qa/AGENTS.md) | Component testing | Frontend TL |
| [Infrastructure TL](agents/infrastructure-team-leader/AGENTS.md) | GitOps, Terraform | CTO |
| [Senior IE](agents/senior-infrastructure-engineer/AGENTS.md) | Pipelines, modules | Infra TL |
| [Junior IE](agents/junior-infrastructure-engineer/AGENTS.md) | Scoped tasks (Flash) | Senior IE |
| [Infra QA](agents/infrastructure-qa/AGENTS.md) | Manifest validation | Infra TL |

## Skills

| Skill | Purpose |
|-------|---------|
| [`teck-conventions`](skills/teck-conventions/SKILL.md) | Cross-repo naming, patterns, rules |
| [`teck-architecture`](skills/teck-architecture/SKILL.md) | Architecture review — boundaries, decomposition |
| [`teck-code-review`](skills/teck-code-review/SKILL.md) | Code review checklist for all four repos |
| [`teck-deployment`](skills/teck-deployment/SKILL.md) | Deployment verification, smoke tests, rollback |

## Usage

```bash
paperclipai company import ./ --target new
paperclipai company import Teck-Lab/Teck.Agents --target new
```

## Model Strategy

- **Junior Engineers** → Deepseek v4 Flash. Single files/services, explicit patterns.
- **Senior Engineers + Database Engineer** → Full-capability models. Complex features.
- **Team Leaders** → v4-pro. Coordination, review, routing. No implementation.
- **CEO/CTO** → gpt-5.5. Strategic decisions. Never implement.

## Execution Stack (OMO Slim)

| OMO Agent | Used By | Primary Model |
|---|---|---|
| Orchestrator | Team Leaders | v4-pro |
| Fixer | Senior + Junior Engineers | k2p7 / v4-flash |
| Oracle | TLs, QA, CTO | v4-pro |
| Librarian | Researchers | v4-flash |
| Explorer | Researchers | v4-flash |
| Designer | Frontend Squad | v4-flash |
| Council | TLs (decisions) | v4-pro |
