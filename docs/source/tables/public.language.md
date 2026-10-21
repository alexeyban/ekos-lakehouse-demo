---
title: "public.language"
order: 111
ekos_generated: true
---

# public.language

<!-- ekos:manual id="source-public.language" -->
_Business meaning of this table, known quirks, data owner._
<!-- /ekos:manual -->

## Columns

| # | Column | Type | Null | Default | Key | References | Allowed values | PII candidate | Comment |
|---|---|---|---|---|---|---|---|---|---|
| 1 | `language_id` | `integer` | NOT NULL | yes | PK |  |  |  |  |
| 2 | `name` | `text` | NOT NULL |  |  |  |  |  |  |
| 3 | `last_update` | `timestamp with time zone` | NOT NULL | yes |  |  |  |  |  |

## Relations

| Direction | Table | Columns | Constraint |
|---|---|---|---|
| ← referenced by | [public.film](../../source/tables/public.film.md) | language_id → language_id | film_language_id_fkey |
| ← referenced by | [public.film](../../source/tables/public.film.md) | original_language_id → language_id | film_original_language_id_fkey |

```mermaid
erDiagram
  public_language {
    integer language_id PK
    text name
    timestamp_with_time_zone last_update
  }
  public_film {
    integer film_id PK
    integer language_id FK
    integer original_language_id FK
  }
  public_film }o--|| public_language : "language_id"
  public_film }o--o| public_language : "original_language_id"
```

## Load into bronze

|  |  |
|---|---|
| Bronze table | `bronze_public.language` |
| Mode | full |
| Hard deletes | replaced with the table |
| Evidence | about 6 rows |
| Notes |  |

Last reconciliation: **✅ green** — control fired. [Details](../../quality/reconciliation.md)

## Downstream

Silver model: [public__language](../../target/silver/tables/public__language.md)

| Column | Silver | Gold | Other models |
|---|---|---|---|
| `language_id` | `public__language.language_id` |  |  |
| `name` | `public__language.name` |  |  |
| `last_update` | `public__language.last_update` |  |  |
