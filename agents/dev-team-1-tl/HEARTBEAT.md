# Dev Team 1 Lead HEARTBEAT

## 0. GitHub Auth
- Mint installation token: `export GITHUB_TOKEN=$(gh auth token --hostname github.com) && export GH_TOKEN=$GITHUB_TOKEN`
- Token expires in 1hr — mint fresh every heartbeat
- Clone repo if needed: `git clone ${REPO_URL} . 2>/dev/null || true`


## 1. Board Check
- Assigned tasks: any new from CTO?
- Spec assignments from CTO: run `/opsx:propose` to create structured spec (v4-pro Orchestrator)
- Senior's tasks: on track? Blocked?
- Open PRs: any waiting for review?

## 2. Code Review
- Review Senior's PRs
- Check Junior BE/FE work for pattern compliance
- Any security issues? Flag to Security Engineer

## 3. Team Health
- Any blocked Juniors? Unblock or escalate
- Any cross-team dependencies with Dev Team 2 or Infra?
- Model spend: are Juniors staying on v4-flash?

## 4. Extraction
- Document decisions made this session
- Update task status on board
- Flag anything needing CTO attention
- On work completion: wake QA Team Lead (POST /api/agents/{qa-tl-id}/wakeup) and CTO (POST /api/agents/{cto-id}/wakeup)

## 5. CI Watch
- Check latest Teck.Cloud CI: `gh run list --repo Teck-Lab/Teck.Cloud --workflow=ci --limit=5`
- Check latest Teck.Web CI: `gh run list --repo Teck-Lab/Teck.Web --workflow=ci --limit=5`
- Any failing builds? Identify failing agent, assign fix to responsible Senior
- Assign fix task, wake Senior: POST /api/agents/{senior-id}/wakeup
- CI red >1hr: escalate to CTO

## 6. Wake-Up Chain
- Senior completes work → wakes you (this is expected, check for wake events)
- On receiving Senior wake: review their work immediately, run full build+test+lint
- Junior completes work → wakes Senior (Junior MUST do this, verify it happened)
- Work stuck >2hrs without wake chain: investigate
