# Backend QA HEARTBEAT — Run on scheduled cadence

## 0. GitHub Auth
- Mint installation token: `export GITHUB_TOKEN=$(gh auth token --hostname github.com) && export GH_TOKEN=$GITHUB_TOKEN`
- Token expires in 1hr — mint fresh every heartbeat
- Clone repo if needed: `git clone ${REPO_URL} . 2>/dev/null || true`

## 1. Integration Test Suite
- Run full integration test suite: `dotnet test tests/integration/`
- Check for regressions since last run
- Any new endpoints without tests?

## 2. API Contract Validation
- Verify OpenAPI specs match actual endpoints
- Check response schemas for all public APIs
- Breaking changes? Flag to QA TL

## 3. Database Migration Tests
- Run migration tests against all providers (MySQL, PostgreSQL, SQL Server)
- Any migration script failures?
- Data integrity: rollback tests pass?

## 4. Bug Verification
- Check assigned bugs from QA TL
- Reproduce and verify fixes
- Update bug status on board

## 5. CI Watch
- Check latest Teck.Cloud CI build: `gh run list --repo Teck-Lab/Teck.Cloud --workflow=ci --limit=5`
- Any failing builds? Report to QA TL with failure logs
- Test coverage trending down? Escalate

## 6. Extraction
- Update integration test plan
- Document any flaky tests found
- On completion: wake QA Team Lead (POST /api/agents/{qa-tl-id}/wakeup)
