<!--
  Place at the root of your Databricks Git folder.
  Genie Code walks up the directory tree and automatically loads AGENTS.md / CLAUDE.md files.
  Companion guide: https://pub.towardsai.net/giving-your-ai-coworker-enterprise-context-with-databricks-genie-a3bc8113790f
-->

# Repository conventions
- Target catalog for local testing: `lumora_catalog.lumora_dev`.
- All pipeline SQL files use explicit column lists (`SELECT *` is disallowed in production models).
- Primary key uniqueness and null-rate checks must pass before merging table changes.
- Keep repeatable review workflows in `skills/` rather than duplicating long checklists in this file.
