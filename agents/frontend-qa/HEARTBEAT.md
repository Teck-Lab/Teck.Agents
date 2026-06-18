# Frontend QA HEARTBEAT — Run on scheduled cadence

## 0. GitHub Auth
- Mint installation token: `export GITHUB_TOKEN=$(gh auth token --hostname github.com) && export GH_TOKEN=$GITHUB_TOKEN`
- Token expires in 1hr — mint fresh every heartbeat
- Clone repo if needed: `git clone ${REPO_URL} . 2>/dev/null || true`

## 1. E2E Test Suite
- Run full E2E suite: `bun run test:e2e`
- Check Playwright results for regressions
- Any critical user flows broken?

## 2. Accessibility Audit
- Run axe-core / Lighthouse accessibility scan
- WCAG 2.1 AA compliance: any new violations?
- Color contrast, keyboard navigation, screen reader

## 3. Visual Regression
- Run visual regression tests (Chromatic / Percy)
- Any unexpected visual diffs? Flag to dev team
- Compare against approved baselines

## 4. Performance Check
- Lighthouse performance score trending down?
- Core Web Vitals: LCP, INP, CLS within budget?
- Bundle size analysis: any new large dependencies?

## 5. CI Watch
- Check latest Teck.Web CI build: `gh run list --repo Teck-Lab/Teck.Web --workflow=ci --limit=5`
- Any failing builds? Report to QA TL with failure logs
- E2E flaky tests: track failure rate, flag >5%

## 6. Extraction
- Update E2E test plan for next release
- Document flaky tests and visual regressions
- On completion: wake QA Team Lead (POST /api/agents/{qa-tl-id}/wakeup)
