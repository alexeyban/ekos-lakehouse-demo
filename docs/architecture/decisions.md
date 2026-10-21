---
title: "Architecture decisions"
order: 21
ekos_generated: true
---

# Architecture decisions

Decisions this data product rests on. Platform decisions come from RFC 0190; per-table decisions are recorded by the generator with their evidence.

## Platform decisions

### ADR-001 — Load engine: Trino connectors

- **Status:** accepted
- **Context:** EKOS must stay out of the data path.
- **Decision:** Trino `postgresql` → `iceberg` connectors move rows; EKOS only generates SQL.
- **Consequences:** Large tables load through one connection unless key-range splitting applies.

### ADR-002 — Change capture: watermark + key-set diff

- **Status:** accepted
- **Context:** No Kafka/Debezium in a self-serve install.
- **Decision:** Incremental only where a BEFORE UPDATE trigger proves the watermark; deletes by key-set diff.
- **Consequences:** Updates without a proven watermark need full loads; reconciliation catches divergence.

### ADR-003 — Transforms: dbt-trino

- **Status:** accepted
- **Context:** Readable, testable code that EKOS can compile back for lineage.
- **Decision:** Silver generated deterministically; gold drafted from descriptions.
- **Consequences:** Hand edits are detected as drift and kept, not overwritten.

### ADR-004 — Orchestrator: Dagster (generated project)

- **Status:** accepted
- **Context:** Asset model matches medallion layers.
- **Decision:** Dagster project generated outside the core.
- **Consequences:** Replaceable later (e.g. Airflow).

### ADR-005 — Catalog: Polaris (Iceberg REST)

- **Status:** accepted
- **Context:** Open REST catalog.
- **Decision:** Bronze, silver and gold are Iceberg tables in Polaris.
- **Consequences:** Pin versions; REST catalogs evolve fast.

### ADR-006 — Gold authorship: draft, check, approve

- **Status:** accepted
- **Context:** Business meaning is never inferred unconfirmed.
- **Decision:** A model drafts gold SQL under an anti-invention check; stakeholder + data engineer approve by merge.
- **Consequences:** Vague descriptions come back as questions.

## Per-table load decisions

| Table | Mode | Watermark | Deletes | Evidence | Notes |
|---|---|---|---|---|---|
| [public.actor](../source/tables/public.actor.md) | full |  | — | about 200 rows |  |
| [public.address](../source/tables/public.address.md) | full |  | — | about 1003 rows |  |
| [public.category](../source/tables/public.category.md) | full |  | — | about 16 rows |  |
| [public.city](../source/tables/public.city.md) | full |  | — | about 600 rows |  |
| [public.country](../source/tables/public.country.md) | full |  | — | about 109 rows |  |
| [public.customer](../source/tables/public.customer.md) | incremental | `last_update` | key-set diff | last_update declared as the watermark in settings; trigger last_updated runs last_updated() before every update and assigns NEW.last_update; last_updated() body sha256 df2a5d93f0f45c50; primary key (customer_id) allows a key-set diff for deletes |  |
| [public.film](../source/tables/public.film.md) | incremental | `last_update` | key-set diff | last_update declared as the watermark in settings; trigger last_updated runs last_updated() before every update and assigns NEW.last_update; last_updated() body sha256 df2a5d93f0f45c50; primary key (film_id) allows a key-set diff for deletes |  |
| [public.film_actor](../source/tables/public.film_actor.md) | full |  | — | about 5462 rows |  |
| [public.film_category](../source/tables/public.film_category.md) | full |  | — | about 2367 rows |  |
| [public.film_embedding](../source/tables/public.film_embedding.md) | full |  | — | about 1000 rows |  |
| [public.inventory](../source/tables/public.inventory.md) | incremental | `last_update` | key-set diff | last_update declared as the watermark in settings; trigger last_updated runs last_updated() before every update and assigns NEW.last_update; last_updated() body sha256 df2a5d93f0f45c50; primary key (inventory_id) allows a key-set diff for deletes |  |
| [public.language](../source/tables/public.language.md) | full |  | — | about 6 rows |  |
| [public.payment](../source/tables/public.payment.md) | full |  | — | about 51061 rows | payment_date is declared, but no BEFORE UPDATE row trigger assigns NEW.payment_date: an update that does not touch it would be missed, so the table is loaded in full |
| [public.rental](../source/tables/public.rental.md) | incremental | `last_update` | key-set diff | last_update declared as the watermark in settings; trigger last_updated runs last_updated() before every update and assigns NEW.last_update; last_updated() body sha256 df2a5d93f0f45c50; primary key (rental_id) allows a key-set diff for deletes |  |
| [public.staff](../source/tables/public.staff.md) | full |  | — | about 1500 rows |  |
| [public.store](../source/tables/public.store.md) | full |  | — | about 500 rows |  |

## Project decisions

<!-- ekos:manual id="adr-project" -->
_Add decisions specific to this project (ADR-1xx): context, decision, consequences, date, approver._
<!-- /ekos:manual -->
