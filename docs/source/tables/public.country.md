---
title: "public.country"
order: 104
ekos_generated: true
---

# public.country

<!-- ekos:manual id="source-public.country" -->
_Business meaning of this table, known quirks, data owner._
<!-- /ekos:manual -->

## Columns

| # | Column | Type | Null | Default | Key | References | Allowed values | PII candidate | Comment |
|---|---|---|---|---|---|---|---|---|---|
| 1 | `country_id` | `integer` | NOT NULL | yes | PK |  |  |  |  |
| 2 | `country` | `text` | NOT NULL |  |  |  |  |  |  |
| 3 | `last_update` | `timestamp with time zone` | NOT NULL | yes |  |  |  |  |  |

## Relations

| Direction | Table | Columns | Constraint |
|---|---|---|---|
| ← referenced by | [public.city](../../source/tables/public.city.md) | country_id → country_id | city_country_id_fkey |

```mermaid
erDiagram
  public_country {
    integer country_id PK
    text country
    timestamp_with_time_zone last_update
  }
  public_city {
    integer city_id PK
    integer country_id FK
  }
  public_city }o--|| public_country : "country_id"
```

## Load into bronze

|  |  |
|---|---|
| Bronze table | `bronze_public.country` |
| Mode | full |
| Hard deletes | replaced with the table |
| Evidence | about 109 rows |
| Notes |  |

Last reconciliation: **✅ green** — control fired. [Details](../../quality/reconciliation.md)

## Downstream

Silver model: [public__country](../../target/silver/tables/public__country.md)

| Column | Silver | Gold | Other models |
|---|---|---|---|
| `country_id` | `public__country.country_id` |  |  |
| `country` | `public__country.country` |  |  |
| `last_update` | `public__country.last_update` |  |  |
