<!--
  Unity Catalog Page template for Genie Ontology.
  Companion guide: https://pub.towardsai.net/giving-your-ai-coworker-enterprise-context-with-databricks-genie-a3bc8113790f
-->

## Active customer

An active customer is a paying customer with at least one `login` event in the last 30 complete calendar days.

- Only `login` events count as product activity.
- `api_call`, `report_run`, and `export` events do not count, because automated integrations can keep running when nobody uses the product.
- Trial and internal test accounts are excluded.
