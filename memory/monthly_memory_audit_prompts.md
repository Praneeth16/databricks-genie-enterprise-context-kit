<!--
  Copy-pasteable prompts to manage private memory in Genie One and Genie Code.
  Companion guide: https://pub.towardsai.net/giving-your-ai-coworker-enterprise-context-with-databricks-genie-a3bc8113790f
-->

# Monthly Memory Audit Prompts

Memories stay private to your user account and go stale over time. Run these checks once a month in both **Genie One** and **Genie Code**.

## 1. Save a personal preference
```text
Remember that when I say "my region" I mean APJ at Lumora.
```
```text
Remember that I want numbers in a table first, then at most three sentences of explanation.
```

## 2. Inspect what Genie remembers vs. instructions
```text
What do you remember about me? Separate saved memories from my instructions file.
```

## 3. Delete stale memories
```text
Forget the memory about my region being APJ. Confirm what memories remain.
```

## 4. Safety check (never store in memory)
- Passwords, tokens, or API keys
- Shared company KPI formulas (move those to Genie Ontology)
- Team-wide coding rules (move those to workspace instructions)
