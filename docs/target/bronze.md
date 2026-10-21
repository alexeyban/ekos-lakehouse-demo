---
title: "Bronze"
order: 41
ekos_generated: true
---

# Bronze

A faithful, append-only copy of each source table. Nothing is cleaned here. Each row carries:

| Column | Meaning |
|---|---|
| `_ekos_loaded_at` | when the row was loaded |
| `_ekos_run_id` | the run that loaded it |
| `_ekos_source_lsn` | source position at load time |
| `_ekos_op` | `delete` for a key-set-diff tombstone |

Iceberg maintenance (snapshot expiry, compaction, orphan files) runs on `0 3 * * *`.

## Tables

| Bronze table | Source | Mode | Watermark | Not exact | Not compared | Health |
|---|---|---|---|---|---|---|
| `bronze_public.actor` | [public.actor](../source/tables/public.actor.md) | full |  |  |  | ✅ healthy |
| `bronze_public.address` | [public.address](../source/tables/public.address.md) | full |  |  |  | ✅ healthy |
| `bronze_public.category` | [public.category](../source/tables/public.category.md) | full |  |  |  | ✅ healthy |
| `bronze_public.city` | [public.city](../source/tables/public.city.md) | full |  |  |  | ✅ healthy |
| `bronze_public.country` | [public.country](../source/tables/public.country.md) | full |  |  |  | ✅ healthy |
| `bronze_public.customer` | [public.customer](../source/tables/public.customer.md) | incremental | `last_update` |  |  | ✅ healthy |
| `bronze_public.film` | [public.film](../source/tables/public.film.md) | incremental | `last_update` | rental_duration (widening), length (widening), fulltext (as_text) | special_features | ✅ healthy |
| `bronze_public.film_actor` | [public.film_actor](../source/tables/public.film_actor.md) | full |  |  |  | ✅ healthy |
| `bronze_public.film_category` | [public.film_category](../source/tables/public.film_category.md) | full |  |  |  | ✅ healthy |
| `bronze_public.film_embedding` | [public.film_embedding](../source/tables/public.film_embedding.md) | full |  |  | embedding | ✅ healthy |
| `bronze_public.inventory` | [public.inventory](../source/tables/public.inventory.md) | incremental | `last_update` |  |  | ✅ healthy |
| `bronze_public.language` | [public.language](../source/tables/public.language.md) | full |  |  |  | ✅ healthy |
| `bronze_public.payment` | [public.payment](../source/tables/public.payment.md) | full |  |  |  | ✅ healthy |
| `bronze_public.rental` | [public.rental](../source/tables/public.rental.md) | incremental | `last_update` |  |  | ✅ healthy |
| `bronze_public.staff` | [public.staff](../source/tables/public.staff.md) | full |  |  |  | ✅ healthy |
| `bronze_public.store` | [public.store](../source/tables/public.store.md) | full |  |  |  | ✅ healthy |

## Type mapping

Every PostgreSQL type maps to an Iceberg type with a lossiness class: `exact`, `widening`, `as_text`, `narrowing_safe` or `refused`.

| PostgreSQL | Iceberg (Trino) | Lossiness | Rule | Columns |
|---|---|---|---|---|
| `boolean` | `boolean` | exact | same | 2 |
| `bytea` | `varbinary` | exact | same | 1 |
| `date` | `date` | exact | same | 1 |
| `integer` | `integer` | exact | same | 37 |
| `mpaa_rating` | `varchar` | exact | enum-label | 1 |
| `numeric(4,2)` | `decimal(4,2)` | exact | same | 2 |
| `numeric(5,2)` | `decimal(5,2)` | exact | same | 2 |
| `smallint` | `integer` | widening | int-widen | 2 |
| `text` | `varchar` | exact | varchar | 22 |
| `text[]` | `array(varchar)` | exact | array | 1 |
| `timestamp with time zone` | `timestamp(6) with time zone` | exact | timestamptz | 18 |
| `tsvector` | `varchar` | as_text | as-text | 1 |
| `uuid` | `uuid` | exact | same | 3 |
| `vector(20)` | `array(real)` | exact | pgvector | 1 |
| `year` | `integer` | exact | domain-base | 1 |
