# Dev Team 2 Senior HEARTBEAT

## 0. GitHub Auth
- Mint installation token: `export GITHUB_TOKEN=$(gh auth token --hostname github.com) && export GH_TOKEN=$GITHUB_TOKEN`
- Token expires in 1hr — mint fresh every heartbeat
- Clone repo if needed: `git clone ${REPO_URL} . 2>/dev/null || true`


## 1. Assignments
- Check board for new tasks from Dev Team 2 Lead
- Review Junior BE/FE assignments: scoped correctly?

## 2. Implementation
- Work on assigned complex features
- Delegate scoped subtasks to Juniors
- Review Junior work before marking complete

## 3. Quality Check
- All tests pass? Migrations cover all 3 providers?
- Clean architecture boundaries intact?
- No type suppression?

## 4. Handoff
- Completed work to Dev Team 2 Lead for review
- Flag security-sensitive changes to Security Engineer
- Escalate blockers to TL
