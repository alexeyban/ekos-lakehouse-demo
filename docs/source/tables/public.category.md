---
title: "public.category"
order: 102
ekos_generated: true
---

# public.category

<!-- ekos:manual id="source-public.category" -->
_Business meaning of this table, known quirks, data owner._
<!-- /ekos:manual -->

## Columns

| # | Column | Type | Null | Default | Key | References | Allowed values | PII candidate | Comment |
|---|---|---|---|---|---|---|---|---|---|
| 1 | `category_id` | `integer` | NOT NULL | yes | PK |  |  |  |  |
| 2 | `name` | `text` | NOT NULL |  |  |  |  |  |  |
| 3 | `last_update` | `timestamp with time zone` | NOT NULL | yes |  |  |  |  |  |

## Relations

| Direction | Table | Columns | Constraint |
|---|---|---|---|
| ← referenced by | [public.film_category](../../source/tables/public.film_category.md) | category_id → category_id | film_category_category_id_fkey |

```mermaid
erDiagram
  public_category {
    integer category_id PK
    text name
    timestamp_with_time_zone last_update
  }
  public_film_category {
    integer film_id PK,FK
    integer category_id PK,FK
  }
  public_film_category }o--|| public_category : "category_id"
```

## Load into bronze

|  |  |
|---|---|
| Bronze table | `bronze_public.category` |
| Mode | full |
| Hard deletes | replaced with the table |
| Evidence | about 16 rows |
| Notes |  |

Last reconciliation: **✅ green** — control fired. [Details](../../quality/reconciliation.md)

## Downstream

Silver model: [public__category](../../target/silver/tables/public__category.md)

| Column | Silver | Gold | Other models |
|---|---|---|---|
| `category_id` | `public__category.category_id` |  |  |
| `name` | `public__category.name` |  |  |
| `last_update` | `public__category.last_update` |  |  |
