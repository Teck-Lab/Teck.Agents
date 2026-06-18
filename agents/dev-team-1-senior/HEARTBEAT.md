# Dev Team 1 Senior HEARTBEAT

## 0. GitHub Auth
- Mint installation token: `export GITHUB_TOKEN=$(gh auth token --hostname github.com) && export GH_TOKEN=$GITHUB_TOKEN`
- Token expires in 1hr — mint fresh every heartbeat
- Clone repo if needed: `git clone ${REPO_URL} . 2>/dev/null || true`


## 1. Assignments
- Check board for new tasks from Dev Team 1 Lead
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
- Completed work to Dev Team 1 Lead for review
- Flag security-sensitive changes to Security Engineer
- Escalate blockers to TL

## 5. Junior Wake Handling
- Junior BE/FE completes work → wakes you (expected, check for wake events)
- On receiving Junior wake: review code, run pre-commit checks, provide feedback
- Junior passes all checks → mark task ready for TL review
- Junior fails checks → send back with specific feedback, do NOT accept

## 6. CI Watch
- Check latest CI builds for your team's repos
- Any failing builds? Fix or assign to responsible Junior
- CI green after your commits: wake TL (POST /api/agents/{tl-id}/wakeup)
