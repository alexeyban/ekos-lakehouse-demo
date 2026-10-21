---
title: "public.film_embedding"
order: 109
ekos_generated: true
---

# public.film_embedding

<!-- ekos:manual id="source-public.film_embedding" -->
_Business meaning of this table, known quirks, data owner._
<!-- /ekos:manual -->

## Columns

| # | Column | Type | Null | Default | Key | References | Allowed values | PII candidate | Comment |
|---|---|---|---|---|---|---|---|---|---|
| 1 | `film_id` | `integer` | NOT NULL |  | PK | [public.film.film_id](../../source/tables/public.film.md) |  |  |  |
| 2 | `embedding` | `vector(20)` | NOT NULL |  |  |  |  |  |  |
| 3 | `last_update` | `timestamp with time zone` | NOT NULL | yes |  |  |  |  |  |

## Relations

| Direction | Table | Columns | Constraint |
|---|---|---|---|
| → references | [public.film](../../source/tables/public.film.md) | film_id → film_id | film_embedding_film_id_fkey |

```mermaid
erDiagram
  public_film_embedding {
    integer film_id PK,FK
    vector embedding
    timestamp_with_time_zone last_update
  }
  public_film {
    integer film_id PK
    integer language_id FK
    integer original_language_id FK
  }
  public_film_embedding }o--|| public_film : "film_id"
```

## Load into bronze

|  |  |
|---|---|
| Bronze table | `bronze_public.film_embedding` |
| Mode | full |
| Hard deletes | replaced with the table |
| Evidence | about 1000 rows |
| Notes |  |

Last reconciliation: **✅ green** — control fired. [Details](../../quality/reconciliation.md)

## Downstream

Silver model: [public__film_embedding](../../target/silver/tables/public__film_embedding.md)

| Column | Silver | Gold | Other models |
|---|---|---|---|
| `film_id` | `public__film_embedding.film_id` |  |  |
| `embedding` | `public__film_embedding.embedding` |  |  |
| `last_update` | `public__film_embedding.last_update` |  |  |
