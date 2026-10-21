---
title: "public.actor"
order: 100
ekos_generated: true
---

# public.actor

<!-- ekos:manual id="source-public.actor" -->
_Business meaning of this table, known quirks, data owner._
<!-- /ekos:manual -->

## Columns

| # | Column | Type | Null | Default | Key | References | Allowed values | PII candidate | Comment |
|---|---|---|---|---|---|---|---|---|---|
| 1 | `actor_id` | `integer` | NOT NULL | yes | PK |  |  |  |  |
| 2 | `first_name` | `text` | NOT NULL |  |  |  |  | personname |  |
| 3 | `last_name` | `text` | NOT NULL |  |  |  |  | personname |  |
| 4 | `last_update` | `timestamp with time zone` | NOT NULL | yes |  |  |  |  |  |

## Relations

| Direction | Table | Columns | Constraint |
|---|---|---|---|
| ← referenced by | [public.film_actor](../../source/tables/public.film_actor.md) | actor_id → actor_id | film_actor_actor_id_fkey |

```mermaid
erDiagram
  public_actor {
    integer actor_id PK
    text first_name
    text last_name
    timestamp_with_time_zone last_update
  }
  public_film_actor {
    integer actor_id PK,FK
    integer film_id PK,FK
  }
  public_film_actor }o--|| public_actor : "actor_id"
```

## Load into bronze

|  |  |
|---|---|
| Bronze table | `bronze_public.actor` |
| Mode | full |
| Hard deletes | replaced with the table |
| Evidence | about 200 rows |
| Notes |  |

Last reconciliation: **✅ green** — control fired. [Details](../../quality/reconciliation.md)

## Downstream

Silver model: [public__actor](../../target/silver/tables/public__actor.md)

| Column | Silver | Gold | Other models |
|---|---|---|---|
| `actor_id` | `public__actor.actor_id` |  |  |
| `first_name` | `public__actor.first_name` |  |  |
| `last_name` | `public__actor.last_name` |  |  |
| `last_update` | `public__actor.last_update` |  |  |
