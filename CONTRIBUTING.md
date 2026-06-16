# CONTRIBUTING.md

## Commit Conventions

All agents must follow this format for commits:

```
[role-shortname]: brief description (#issue-number)
```

Examples:
- `[senior-be]: add LocationValidator to Order service (#42)`
- `[infra-tl]: bump cert-manager chart to 1.17 (#58)`
- `[qa-tl]: verify Kargo production promotion (#73)`

## Branch Strategy

- **Default**: work directly on `main` (trunk-based)
- **Complex features**: create branch `feature/<slug>`, merge via PR
- **Infra changes**: always via PR with Terraform plan in description

## After-Completion Ritual

1. Commit with conventional message
2. Update Paperclip issue status
3. Comment on issue with commit hash
4. If PR: assign reviewer (Dev TL or Security Engineer for sensitive changes)

## File Ownership

| File Pattern | Owner | Review Required |
|---|---|---|
| `*.cs` (Teck.Cloud) | Dev Teams | Senior review |
| `*.tsx`, `*.ts` (Teck.Web) | Dev Teams | Senior review |
| `*.yaml` (Teck.GitOps) | Infra Team | Infra TL review |
| `*.tf` (Teck.Terraform) | Infra Team | Infra TL + Security review |
| `*.yml` (CI/CD) | Infra Team | Infra TL review |
| `*.sql` (migrations) | Database Engineer | Senior review |

## PR Gates

- All tests pass (unit + integration)
- No hard-coded secrets or image tags
- Clean architecture boundaries intact
- Security review for: auth changes, new endpoints, dependency additions
