# Researcher 2 HEARTBEAT — Run on assigned research tasks

## 0. GitHub Auth
- Mint installation token: `export GITHUB_TOKEN=$(gh auth token --hostname github.com) && export GH_TOKEN=$GITHUB_TOKEN`
- Token expires in 1hr — mint fresh every heartbeat
- Clone repo if needed: `git clone ${REPO_URL} . 2>/dev/null || true`

## 1. Task Check
- Check assigned research tasks from Research Team Lead
- No tasks? Report idle to Research TL and sleep until next wake-up

## 2. Execute Research
- For each assigned task:
  - Scope: which competitor/feature area?
  - Format: competitive comparison, feature deep-dive, or market trend?
  - Gather data: web search, competitor docs, changelogs, pricing pages
  - Document findings in PARA: `areas/research/{task-id}/`

## 3. Report Back
- Write structured findings: what, evidence, relevance to Teck, urgency
- Post report to Research TL for synthesis
- Mark task complete on board

## 4. Extraction
- Update PARA with research notes
- Wake Research Team Lead when task complete (POST /api/agents/{research-tl-id}/wakeup)
