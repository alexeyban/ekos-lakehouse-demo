---
title: "Runbook"
order: 81
ekos_generated: true
---

# Runbook

## Schedules

| Job | Cron |
|---|---|
| Bronze loads | `0 * * * *` |
| Iceberg maintenance | `0 3 * * *` |

## Everyday commands

```bash
ekos-lakehouse lakehouse doctor            # which services answer
ekos-lakehouse lakehouse status            # health per table and layer
ekos-lakehouse lakehouse reconcile         # V1–V3 with a planted control
ekos-lakehouse lakehouse check --lint      # lineage, coverage, drift, lint
ekos-lakehouse lakehouse sync              # apply safe source changes, propose the rest
ekos-lakehouse lakehouse proposals         # what waits for a merge
ekos-lakehouse lakehouse reload --table <schema.table>   # full reload on the next run
```

## By health state

| State | Meaning | First action |
|---|---|---|
| late | no successful run within `late-after-minutes` | check Dagster for a stuck or failed run; `lakehouse doctor` |
| failing | the last run or a test failed | read the cause in `lakehouse status`; failing silver tests link to the source change or data finding |
| unverified | reconciliation agreed but the planted control was missed | rerun `lakehouse reconcile --table …`; do not trust the table until green |
| schema_pending | a breaking source change waits on a proposal | review the branch `ekos/change/<table>/<id>`; merging is the approval |
| diverged (reconciliation) | bronze differs from the source | check watermark validity; `lakehouse reload --table …` if the watermark missed updates |

## Contacts and escalation

<!-- ekos:manual id="runbook-contacts" -->
_On-call rotation, escalation path, source-system DBA contact._
<!-- /ekos:manual -->

## Known issues

<!-- ekos:manual id="runbook-known-issues" -->
_Recurring incidents and their fixes._
<!-- /ekos:manual -->
