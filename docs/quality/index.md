---
title: "Data quality & reconciliation"
order: 60
ekos_generated: true
---

# Data quality & reconciliation

> Evidence collected 2026-10-21 15:32 UTC at pipeline commit `efeeffd`.

| Area | Result |  | Notes |
|---|---|---|---|
| [Source ↔ bronze reconciliation](../quality/reconciliation.md) | 16 green, 0 diverged, 0 unverified | ✅ | planted controls missed: 0 |
| [dbt data tests](../quality/data-tests.md) | 114 defined, no run results | — |  |
| [Code quality (lakehouse check)](../quality/code-quality.md) | 7/7 metrics met | ✅ |  |
| [Pipeline health](../quality/health.md) | healthy: 32 | ✅ |  |

## What is checked, and how

| Check | Layer | How |
|---|---|---|
| Reconciliation | source → bronze | row counts, then bucketed canonical checksums (V1–V3), with a planted one-row control that must be detected |
| Key uniqueness / not-null / relationships / accepted values | silver | dbt tests generated from source constraints, each naming its evidence |
| Grain uniqueness, measure reconciliation | gold | dbt tests generated with the mart |
| Lineage, test & doc coverage, drift, lint | code | `lakehouse check --lint` |
| Freshness, failures, unverified runs, schema pending | all | `lakehouse status` from run facts |

## Sign-off

<!-- ekos:manual id="quality-signoff" -->
_UAT / reconciliation sign-off: who verified, when, against which evidence run._
<!-- /ekos:manual -->
