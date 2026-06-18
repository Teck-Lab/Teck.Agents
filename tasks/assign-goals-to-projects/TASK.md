---
name: Assign Goals to Projects
slug: assign-goals-to-projects
assignee: ceo
project: teck-cloud
schedule:
  startsAt: 2026-06-17T00:00:00Z
  timezone: UTC
---
Assign all company goals to the correct projects so they're visible in the project view.

1. List all goals: GET /api/companies/:companyId/goals
2. For each goal, determine the correct project (see GOALS.md for mapping)
3. Assign via PATCH /api/projects/:projectId/goals/:goalId
4. Report which goals were assigned to which projects
