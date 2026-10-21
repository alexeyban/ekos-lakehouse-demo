---
title: "Pagila rentals (EKOS Lakehouse sandbox) — data documentation"
order: 0
ekos_generated: true
---

# Pagila rentals (EKOS Lakehouse sandbox) — data documentation

<!-- ekos:manual id="home-intro" -->
_A one-paragraph introduction for readers new to this data product._
<!-- /ekos:manual -->

## At a glance

|  | Value |
|---|---|
| Source tables (planned / refused) | 16 / 0 |
| Source columns | 95 |
| Silver models | 16 |
| Gold marts | 0 |
| Other dbt models (e.g. Pentaho translations) | 0 |
| Generated dbt tests | 114 |
| Reconciliation (green / diverged / unverified) | 16 / 0 / 0 |
| Health states | healthy: 32 |
| Proposals in the repository | 1 |

## Contents

| Section | What it covers |
|---|---|
| [Business description](business/index.md) | purpose, scope, owners, consumers, KPIs |
| [Glossary](business/glossary.md) | business terms and where each is implemented |
| [Architecture](architecture/index.md) | components, data flow, layers, conventions |
| [Architecture decisions](architecture/decisions.md) | platform and per-table decisions with their evidence |
| [Source](source/index.md) | tables, keys, relations, ER diagram |
| [Target](target/index.md) | bronze, silver and gold — tables, relations, ER diagrams |
| [Lineage](lineage/index.md) | table- and column-level, source to gold |
| [Data quality & reconciliation](quality/index.md) | checks, tests, code quality, health |
| [Governance](governance/index.md) | data dictionary, PII and masking |
| [Operations](operations/index.md) | runbook, SLAs, schema changes, change log |

## Provenance

Every page is generated from the deployed plan (`lakehouse.lock.json`), the generated dbt project, mart descriptions, proposals, git history and collected run evidence. Edit only inside the marked manual sections — regeneration keeps them and replaces everything else.

|  |  |
|---|---|
| Pipeline repository | `pipeline` |
| Pipeline commit | `efeeffd` |
| Plan format | 3 |
| Source catalog (Trino) | `pagila` |
| Target catalog (Iceberg) | `iceberg` |
| Evidence collected | 2026-10-21 15:32 UTC |
| Generated | 2026-10-21 |
