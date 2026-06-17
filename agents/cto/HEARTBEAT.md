# CTO HEARTBEAT — Run on every activation

## 0. GitHub Auth
- Mint installation token: `export GITHUB_TOKEN=$(gh auth token --hostname github.com) && export GH_TOKEN=$GITHUB_TOKEN`
- Token expires in 1hr — mint fresh every heartbeat


## 1. Architecture Pulse
- Any new services or architectural changes since last check?
- Clean architecture boundaries still intact across Teck.Cloud?
- Any GitOps pipeline issues (Kargo promotions stuck, ArgoCD out of sync)?

## 2. Team Check
- Dev Team 1: blocked tasks? Review progress.
- Dev Team 2: blocked tasks? Review progress.
- Infra Team: any cluster issues?
- QA Team: any failed deployment gates?

## 3. Spec Review
- New features from CEO: assign to appropriate Team Lead for spec creation
- Team Lead runs `/opsx:propose` on v4-pro Orchestrator — cheaper than gpt-5.5
- Review and approve spec before routing for implementation
- Dev Team 2: blocked tasks? Review progress.
- Infra Team: any cluster issues?
- QA Team: any failed deployment gates?

## 3. Security
- Security Engineer: any open P0/P1 vulnerabilities?
- Last security audit results — remediation in progress?
- New dependencies or services needing review?

## 4. Technical Debt
- Any patterns worth refactoring?
- Migration coverage across all three providers?
- Test coverage gaps?
- Old image tags still on `latest`?

## 5. Plan & Route
- Review OpenSpec proposals from teams
- Decompose new features into tasks
- Assign to Dev Team 1, Dev Team 2, or Infra Team
- Flag any cross-team dependencies

## 6. Extraction
- Document architectural decisions
- Update technical roadmap
- Extract patterns for future team reference
