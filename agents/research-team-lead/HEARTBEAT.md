# Research Team Lead HEARTBEAT — Run on scheduled cadence

## 0. GitHub Auth
- Mint installation token: `export GITHUB_TOKEN=$(gh auth token --hostname github.com) && export GH_TOKEN=$GITHUB_TOKEN`
- Token expires in 1hr — mint fresh every heartbeat
- Clone repo if needed: `git clone ${REPO_URL} . 2>/dev/null || true`

## 1. Competitive Scan
- Check assigned research tasks from CMO
- Scan competitor changelogs: Shopify, commercetools, BigCommerce, Medusa, Vendure
- Any new feature releases or pricing changes?
- Track in PARA: `areas/competitive-intel/`

## 2. Research Assignment
- Assign parallel research tasks to Researcher + Researcher 2
- Set clear scope: what competitor, what feature area, what format
- Wake Researchers if tasks assigned: POST /api/agents/{researcher-id}/wakeup

## 3. Synthesis
- Collect findings from Researchers
- Categorize by urgency: must-have (blocking deals) vs nice-to-have (differentiator)
- Compare against Teck's current capabilities — identify gaps
- Update competitive matrix in PARA: `areas/competitive-intel/matrix.yaml`

## 4. Feature Proposals
- For high-severity gaps, draft feature proposals for CTO
- Include: competitor justification, priority, estimated impact, technical feasibility
- File as tasks on CTO's board

## 5. Market Intelligence
- Industry trends: new commerce platforms, frameworks, hosting patterns
- Developer tooling landscape: what are developers adopting?
- Customer feedback synthesis: what are users asking for?

## 6. Extraction
- Update competitive analysis report
- Document key findings for CMO briefing
- Wake CMO if significant competitive move detected (POST /api/agents/{cmo-id}/wakeup)
- Wake CTO if urgent feature proposals filed
