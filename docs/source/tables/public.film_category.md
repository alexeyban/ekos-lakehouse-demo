---
title: "public.film_category"
order: 108
ekos_generated: true
---

# public.film_category

<!-- ekos:manual id="source-public.film_category" -->
_Business meaning of this table, known quirks, data owner._
<!-- /ekos:manual -->

## Columns

| # | Column | Type | Null | Default | Key | References | Allowed values | PII candidate | Comment |
|---|---|---|---|---|---|---|---|---|---|
| 1 | `film_id` | `integer` | NOT NULL |  | PK | [public.film.film_id](../../source/tables/public.film.md) |  |  |  |
| 2 | `category_id` | `integer` | NOT NULL |  | PK | [public.category.category_id](../../source/tables/public.category.md) |  |  |  |
| 3 | `last_update` | `timestamp with time zone` | NOT NULL | yes |  |  |  |  |  |

## Relations

| Direction | Table | Columns | Constraint |
|---|---|---|---|
| → references | [public.category](../../source/tables/public.category.md) | category_id → category_id | film_category_category_id_fkey |
| → references | [public.film](../../source/tables/public.film.md) | film_id → film_id | film_category_film_id_fkey |

```mermaid
erDiagram
  public_film_category {
    integer film_id PK,FK
    integer category_id PK,FK
    timestamp_with_time_zone last_update
  }
  public_category {
    integer category_id PK
  }
  public_film {
    integer film_id PK
    integer language_id FK
    integer original_language_id FK
  }
  public_film_category }o--|| public_category : "category_id"
  public_film_category }o--|| public_film : "film_id"
```

## Load into bronze

|  |  |
|---|---|
| Bronze table | `bronze_public.film_category` |
| Mode | full |
| Hard deletes | replaced with the table |
| Evidence | about 2367 rows |
| Notes |  |

Last reconciliation: **✅ green** — control fired. [Details](../../quality/reconciliation.md)

## Downstream

Silver model: [public__film_category](../../target/silver/tables/public__film_category.md)

| Column | Silver | Gold | Other models |
|---|---|---|---|
| `film_id` | `public__film_category.film_id` |  |  |
| `category_id` | `public__film_category.category_id` |  |  |
| `last_update` | `public__film_category.last_update` |  |  |
