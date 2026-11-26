<!--
  Unity Catalog Page template for Genie Ontology.
  Companion guide: https://pub.towardsai.net/giving-your-ai-coworker-enterprise-context-with-databricks-genie-a3bc8113790f
-->

## Monthly recurring revenue (MRR)

MRR measures normalized monthly subscription revenue in USD across active paying subscriptions.

- For monthly plans, use `amount` directly.
- For annual plans, Lumora stores the full yearly price in `amount`, so divide `amount` by 12.
- Exclude canceled, trial, and internal demo accounts.

## Net customer churn

A churned customer is a paying account whose final active subscription ended without an upgrade or renewal within the same fiscal quarter.

- Do not count plan upgrades (where a lower-tier subscription is marked `canceled` and replaced by a higher-tier `active` subscription) as churn.
- Group churn by Lumora's fiscal quarter (see the Fiscal calendar page).
