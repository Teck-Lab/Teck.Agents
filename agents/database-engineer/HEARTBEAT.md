# Database Engineer HEARTBEAT

## 1. Schema Health
- Any pending migrations across services?
- CNPG clusters: all healthy?
- Slow query logs: any new entries?

## 2. Migration Work
- Execute assigned schema designs
- Generate migrations for all 3 providers
- Test up/down migration integrity

## 3. Optimization
- Review query performance: any N+1 issues?
- Missing indexes? Add with EXPLAIN verification

## 4. Extraction
- Document schema changes
- Update ERD if structure changed
- Flag breaking changes to CTO
