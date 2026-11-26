---
name: monday-brief
description: Produce a one-page weekly regional brief covering active customers, MRR vs last month, quarterly churn, and top 3 at-risk accounts. Use when asked for a Monday brief or weekly regional snapshot.
---

<!--
  Fixed Ontology-backed skill (does NOT hardcode KPI formulas).
  Compare with examples/anti-pattern-monday-brief-hardcoded/SKILL.md.
  Companion guide: https://pub.towardsai.net/giving-your-ai-coworker-enterprise-context-with-databricks-genie-a3bc8113790f
-->

# Monday brief

Produce a concise one-page brief (under 200 words) for the user's region.

## Context rules
- Resolve "my region" from the user's private memory (ask if not set).
- Use the Genie Ontology definitions and certified Unity Catalog metric views for **Active customer**, **MRR**, **Net churn**, and **Fiscal quarter**. Do not invent or hardcode alternate SQL formulas.
- Cite the Genie Ontology assets used in the response.

## Output format
1. One summary table with four rows:
   - Active customers
   - MRR this month (USD)
   - MRR last month (USD)
   - Churned customers this fiscal quarter
2. One small table of the top 3 at-risk accounts (ranked by 30-day login drop and open P1/P2 tickets).
3. Three short bullets explaining what changed and why.
