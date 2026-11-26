---
name: pipeline-review
description: Review a Lumora pipeline or table change before it ships. Use when asked to review, check, or sign off a pipeline, a new table, or a change to an existing table.
---

<!-- Companion guide: https://pub.towardsai.net/giving-your-ai-coworker-enterprise-context-with-databricks-genie-a3bc8113790f -->

# Pipeline review

Run these checks in order. Report each one as PASS or FAIL with one line of evidence.

1. Comments. The table has a table comment and every column has a column comment.
2. Schema. New tables are in `lumora_dev`, not `lumora`.
3. Row count. Compare the row count with the source. Flag any drop or growth above 5 percent.
4. Nulls. List key columns (ids, dates, amounts) where more than 1 percent of rows are null.
5. Duplicates. Check that the primary key is unique.
6. Definitions. If the table computes customers, MRR, or churn, check the logic against the Genie Ontology definition rather than guessing.

End with one verdict: ship, ship with fixes, or do not ship. Do not modify any table during a review.
