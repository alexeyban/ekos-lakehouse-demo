---
title: "Code quality"
order: 63
ekos_generated: true
---

# Code quality

> Evidence collected 2026-10-21 15:32 UTC at pipeline commit `efeeffd`.

`lakehouse check --lint` measures the generated project: lineage completeness (the dbt project compiled back into the EKOS ledger), test and documentation coverage, drift from generated code and `sqlfluff` lint.

| Metric | Measured | Passed | Method | Gaps |
|---|---|---|---|---|
| lineage | 111/111 | ✅ | each silver column's column_lineage in the ledger (EKOS dbt analyzer) equals its bronze column; masked columns excluded as computed |  |
| test_coverage.keys | 16/16 | ✅ | models with a key that test it unique, from the model YAML in dbt/models/silver/ |  |
| test_coverage.not_null | 78/78 | ✅ | NOT NULL and key columns with a not_null test, from the model YAML in dbt/models/silver/ |  |
| test_coverage.relationships | 19/19 | ✅ | single-column foreign keys to planned tables with a relationships test, from the model YAML in dbt/models/silver/ |  |
| documentation | 0/111 | ✅ | models and columns with a description, from the model YAML in dbt/models/silver/ |  |
| drift | 92/92 | ✅ | each generated file against the manifest of what generate wrote (edits) and against what the deployed plan generates now (staleness) |  |
| lint | 18/18 | ✅ | sqlfluff lint with the generated .sqlfluff (dialect trino, core rules) |  |
