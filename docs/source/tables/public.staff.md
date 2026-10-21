---
title: "public.staff"
order: 114
ekos_generated: true
---

# public.staff

<!-- ekos:manual id="source-public.staff" -->
_Business meaning of this table, known quirks, data owner._
<!-- /ekos:manual -->

## Columns

| # | Column | Type | Null | Default | Key | References | Allowed values | PII candidate | Comment |
|---|---|---|---|---|---|---|---|---|---|
| 1 | `staff_id` | `integer` | NOT NULL | yes | PK |  |  |  |  |
| 2 | `first_name` | `text` | NOT NULL |  |  |  |  | personname |  |
| 3 | `last_name` | `text` | NOT NULL |  |  |  |  | personname |  |
| 4 | `address_id` | `integer` | NOT NULL |  |  | [public.address.address_id](../../source/tables/public.address.md) |  | postaladdress |  |
| 5 | `email` | `text` | null |  |  |  |  | email |  |
| 6 | `store_id` | `integer` | NOT NULL |  |  | [public.store.store_id](../../source/tables/public.store.md) |  |  |  |
| 7 | `active` | `boolean` | NOT NULL | yes |  |  |  |  |  |
| 8 | `username` | `text` | NOT NULL |  |  |  |  |  |  |
| 9 | `password` | `text` | null |  |  |  |  | credential |  |
| 10 | `last_update` | `timestamp with time zone` | NOT NULL | yes |  |  |  |  |  |
| 11 | `picture` | `bytea` | null |  |  |  |  |  |  |

## Relations

| Direction | Table | Columns | Constraint |
|---|---|---|---|
| → references | [public.address](../../source/tables/public.address.md) | address_id → address_id | staff_address_id_fkey |
| → references | [public.store](../../source/tables/public.store.md) | store_id → store_id | staff_store_id_fkey |
| ← referenced by | [public.rental](../../source/tables/public.rental.md) | staff_id → staff_id | rental_staff_id_fkey |

```mermaid
erDiagram
  public_staff {
    integer staff_id PK
    text first_name
    text last_name
    integer address_id FK
    text email
    integer store_id FK
    boolean active
    text username
    text password
    timestamp_with_time_zone last_update
    bytea picture
  }
  public_address {
    integer address_id PK
    integer city_id FK
  }
  public_store {
    integer store_id PK
    integer address_id FK
  }
  public_rental {
    integer rental_id PK
    integer inventory_id FK
    integer customer_id FK
    integer staff_id FK
  }
  public_staff }o--|| public_address : "address_id"
  public_staff }o--|| public_store : "store_id"
  public_store }o--|| public_address : "address_id"
  public_rental }o--|| public_staff : "staff_id"
```

## Load into bronze

|  |  |
|---|---|
| Bronze table | `bronze_public.staff` |
| Mode | full |
| Hard deletes | replaced with the table |
| Evidence | about 1500 rows |
| Notes |  |

Last reconciliation: **✅ green** — control fired. [Details](../../quality/reconciliation.md)

## Downstream

Silver model: [public__staff](../../target/silver/tables/public__staff.md)

| Column | Silver | Gold | Other models |
|---|---|---|---|
| `staff_id` | `public__staff.staff_id` |  |  |
| `first_name` | `public__staff.first_name` |  |  |
| `last_name` | `public__staff.last_name` |  |  |
| `address_id` | `public__staff.address_id` |  |  |
| `email` | `public__staff.email` |  |  |
| `store_id` | `public__staff.store_id` |  |  |
| `active` | `public__staff.active` |  |  |
| `username` | `public__staff.username` |  |  |
| `password` | `public__staff.password` |  |  |
| `last_update` | `public__staff.last_update` |  |  |
| `picture` | `public__staff.picture` |  |  |
