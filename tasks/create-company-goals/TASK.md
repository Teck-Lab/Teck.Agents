---
name: Create Company Goals
slug: create-company-goals
assignee: cto
project: teck-cloud
schedule:
  startsAt: 2026-06-17T00:00:00Z
  timezone: UTC
---
Create the company goals from GOALS.md in the Teck.Agents repo.

1. Read GOALS.md from the company package
2. Create all 14 parent goals via POST /api/companies/:id/goals with type, status, and owner
3. For each parent, create sub-goals with parentId set to the returned goal ID
4. Use status "planned" for MVP goals and "proposed" for Post-MVP goals
5. Report back with the created goal IDs and any issues
