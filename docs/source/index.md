---
title: "Source"
order: 30
ekos_generated: true
---

# Source

Source: **PostgreSQL 18 (Pagila)**, read through Trino catalog `pagila`. [ER diagram](../source/er-diagram.md) · [Column lineage](../lineage/column-lineage.md)

<!-- ekos:manual id="source-description" -->
Pagila, the DVD-rental sample database for PostgreSQL, loaded into the sandbox's lh-postgres by deploy/fixtures/pagila.sh (pinned to commit 9baf49c, checked by SHA-256). Used here as the demo source; it is not a production system.
<!-- /ekos:manual -->

## Tables

| Table | Columns | Primary key | FKs out | Referenced by | Load | PII candidates | Description |
|---|---|---|---|---|---|---|---|
| [public.actor](../source/tables/public.actor.md) | 4 | actor_id | 0 | 1 | full | first_name, last_name |  |
| [public.address](../source/tables/public.address.md) | 8 | address_id | 1 | 3 | full | address_id, address, address2, postal_code, phone |  |
| [public.category](../source/tables/public.category.md) | 3 | category_id | 0 | 1 | full |  |  |
| [public.city](../source/tables/public.city.md) | 4 | city_id | 1 | 1 | full |  |  |
| [public.country](../source/tables/public.country.md) | 3 | country_id | 0 | 1 | full |  |  |
| [public.customer](../source/tables/public.customer.md) | 12 | customer_id | 2 | 1 | incremental | first_name, last_name, email, address_id |  |
| [public.film](../source/tables/public.film.md) | 15 | film_id | 2 | 4 | incremental |  |  |
| [public.film_actor](../source/tables/public.film_actor.md) | 3 | actor_id, film_id | 2 | 0 | full |  |  |
| [public.film_category](../source/tables/public.film_category.md) | 3 | film_id, category_id | 2 | 0 | full |  |  |
| [public.film_embedding](../source/tables/public.film_embedding.md) | 3 | film_id | 1 | 0 | full |  |  |
| [public.inventory](../source/tables/public.inventory.md) | 4 | inventory_id | 2 | 1 | incremental |  |  |
| [public.language](../source/tables/public.language.md) | 3 | language_id | 0 | 2 | full |  |  |
| [public.payment](../source/tables/public.payment.md) | 7 | payment_date, payment_id | 0 | 0 | full |  |  |
| [public.rental](../source/tables/public.rental.md) | 8 | rental_id | 3 | 0 | incremental |  |  |
| [public.staff](../source/tables/public.staff.md) | 11 | staff_id | 2 | 1 | full | first_name, last_name, address_id, email, password |  |
| [public.store](../source/tables/public.store.md) | 4 | store_id | 1 | 3 | full | address_id |  |

## Refused tables

_None: every source table has a faithful landing._
