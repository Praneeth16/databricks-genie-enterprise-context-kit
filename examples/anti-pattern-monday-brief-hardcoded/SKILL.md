---
name: monday-brief-hardcoded-antipattern
description: ANTI-PATTERN EXAMPLE ONLY. Do not install in production. Demonstrates what happens when a skill hardcodes KPI formulas instead of referencing Genie Ontology.
---

<!--
  ANTI-PATTERN EXAMPLE from the Lumora hands-on test (catalog name scrubbed to lumora_catalog).
  Full walkthrough of the 3 bugs frozen here:
  https://pub.towardsai.net/giving-your-ai-coworker-enterprise-context-with-databricks-genie-a3bc8113790f
-->

# Why this skill breaks every Monday

When Genie One built this skill in a shared workspace, it pulled an unrelated glossary page and froze three wrong rules inside `SKILL.md`:

1. **Overstated MRR:** `SUM(s.amount)` summed raw annual subscription prices without dividing annual plans by 12.
2. **Wrong fiscal quarter:** `DATE_TRUNC('quarter', CURRENT_DATE())` used calendar quarters instead of Lumora's February 1 fiscal year start.
3. **Inflated churn:** `WHERE s.status = 'canceled'` counted every canceled row as churn, including customers who upgraded to a higher plan.

## The frozen SQL that caused all three errors

```sql
-- BUG 1: misses dividing annual plans by 12
SELECT SUM(s.amount) AS mrr_usd
FROM lumora_catalog.lumora.subscriptions s
WHERE s.status = 'active';

-- BUG 2 & 3: calendar quarter (not Feb 1 FY) + counts plan upgrades as churn
SELECT COUNT(DISTINCT s.account_id) AS churned_customers
FROM lumora_catalog.lumora.subscriptions s
WHERE s.status = 'canceled'
  AND s.end_date >= DATE_TRUNC('quarter', CURRENT_DATE());
```

## Fix
See `skills/monday-brief/SKILL.md`: keep workflow steps in the skill, and tell Genie to resolve **MRR**, **Active customer**, **Fiscal quarter**, and **Net churn** from **Genie Ontology** instead.
