# CTO HEARTBEAT — Run on every activation

## 0. GitHub Auth
- Mint installation token: `export GITHUB_TOKEN=$(gh auth token --hostname github.com) && export GH_TOKEN=$GITHUB_TOKEN`
- Token expires in 1hr — mint fresh every heartbeat
- Clone repo if needed: `git clone ${REPO_URL} . 2>/dev/null || true`

## 1. Architecture Pulse
- Any new services or architectural changes since last check?
- Clean architecture boundaries still intact across Teck.Cloud?
- Any GitOps pipeline issues (Kargo promotions stuck, ArgoCD out of sync)?

## 2. Iterate — Scan & Create Work
- **Unassigned tasks**: list all issues without assignee, route to appropriate team lead
- **Blocked tasks**: review blocked issues, unblock or reassign if stuck >24h
- **Approved specs**: run `/opsx:apply` on approved OpenSpec proposals → decompose into tasks
- **Goals without tasks**: check active company goals, create implementation tasks for goals without assigned issues
- **Stale tasks**: review tasks idle >7 days, reassign or close

## 3. Team Check
- Dev Team 1: blocked tasks? Review progress.
- Dev Team 2: blocked tasks? Review progress.
- Infra Team: any cluster issues?
- QA Team: any failed deployment gates?

## 4. Spec Review
- New features from CEO: assign to appropriate Team Lead for spec creation
- Team Lead runs `/opsx:propose` on v4-pro Orchestrator — cheaper than gpt-5.5
- Review and approve spec before routing for implementation

## 5. Security
- Security Engineer: any open P0/P1 vulnerabilities?
- Last security audit results — remediation in progress?
- New dependencies or services needing review?

## 6. Plan & Route
- Review OpenSpec proposals from teams
- Decompose new features into tasks with clear acceptance criteria
- Assign tasks to Dev Team 1, Dev Team 2, or Infra Team based on domain
- Flag cross-team dependencies and create coordination tasks

## 7. Extraction
- Document architectural decisions
- Update technical roadmap
- Extract patterns for future team reference
