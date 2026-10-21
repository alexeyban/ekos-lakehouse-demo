---
title: "Lineage"
order: 50
ekos_generated: true
---

# Lineage

Table-level lineage from the source through bronze and silver to gold. Column-level lineage is on [Column lineage (source-to-target mapping)](../lineage/column-lineage.md) and on every table page.

```mermaid
flowchart LR
  subgraph L_source["Source"]
    source_public_actor[("public.actor")]
    source_public_address[("public.address")]
    source_public_category[("public.category")]
    source_public_city[("public.city")]
    source_public_country[("public.country")]
    source_public_customer[("public.customer")]
    source_public_film[("public.film")]
    source_public_film_actor[("public.film_actor")]
    source_public_film_category[("public.film_category")]
    source_public_film_embedding[("public.film_embedding")]
    source_public_inventory[("public.inventory")]
    source_public_language[("public.language")]
    source_public_payment[("public.payment")]
    source_public_rental[("public.rental")]
    source_public_staff[("public.staff")]
    source_public_store[("public.store")]
  end
  subgraph L_bronze["Bronze"]
    bronze_bronze_public_actor["bronze_public.actor"]
    bronze_bronze_public_address["bronze_public.address"]
    bronze_bronze_public_category["bronze_public.category"]
    bronze_bronze_public_city["bronze_public.city"]
    bronze_bronze_public_country["bronze_public.country"]
    bronze_bronze_public_customer["bronze_public.customer"]
    bronze_bronze_public_film["bronze_public.film"]
    bronze_bronze_public_film_actor["bronze_public.film_actor"]
    bronze_bronze_public_film_category["bronze_public.film_category"]
    bronze_bronze_public_film_embedding["bronze_public.film_embedding"]
    bronze_bronze_public_inventory["bronze_public.inventory"]
    bronze_bronze_public_language["bronze_public.language"]
    bronze_bronze_public_payment["bronze_public.payment"]
    bronze_bronze_public_rental["bronze_public.rental"]
    bronze_bronze_public_staff["bronze_public.staff"]
    bronze_bronze_public_store["bronze_public.store"]
  end
  subgraph L_silver["Silver"]
    silver_public__actor["public__actor"]
    silver_public__address["public__address"]
    silver_public__category["public__category"]
    silver_public__city["public__city"]
    silver_public__country["public__country"]
    silver_public__customer["public__customer"]
    silver_public__film["public__film"]
    silver_public__film_actor["public__film_actor"]
    silver_public__film_category["public__film_category"]
    silver_public__film_embedding["public__film_embedding"]
    silver_public__inventory["public__inventory"]
    silver_public__language["public__language"]
    silver_public__payment["public__payment"]
    silver_public__rental["public__rental"]
    silver_public__staff["public__staff"]
    silver_public__store["public__store"]
  end
  bronze_bronze_public_actor --> silver_public__actor
  bronze_bronze_public_address --> silver_public__address
  bronze_bronze_public_category --> silver_public__category
  bronze_bronze_public_city --> silver_public__city
  bronze_bronze_public_country --> silver_public__country
  bronze_bronze_public_customer --> silver_public__customer
  bronze_bronze_public_film --> silver_public__film
  bronze_bronze_public_film_actor --> silver_public__film_actor
  bronze_bronze_public_film_category --> silver_public__film_category
  bronze_bronze_public_film_embedding --> silver_public__film_embedding
  bronze_bronze_public_inventory --> silver_public__inventory
  bronze_bronze_public_language --> silver_public__language
  bronze_bronze_public_payment --> silver_public__payment
  bronze_bronze_public_rental --> silver_public__rental
  bronze_bronze_public_staff --> silver_public__staff
  bronze_bronze_public_store --> silver_public__store
  source_public_actor --> bronze_bronze_public_actor
  source_public_address --> bronze_bronze_public_address
  source_public_category --> bronze_bronze_public_category
  source_public_city --> bronze_bronze_public_city
  source_public_country --> bronze_bronze_public_country
  source_public_customer --> bronze_bronze_public_customer
  source_public_film --> bronze_bronze_public_film
  source_public_film_actor --> bronze_bronze_public_film_actor
  source_public_film_category --> bronze_bronze_public_film_category
  source_public_film_embedding --> bronze_bronze_public_film_embedding
  source_public_inventory --> bronze_bronze_public_inventory
  source_public_language --> bronze_bronze_public_language
  source_public_payment --> bronze_bronze_public_payment
  source_public_rental --> bronze_bronze_public_rental
  source_public_staff --> bronze_bronze_public_staff
  source_public_store --> bronze_bronze_public_store
```

| Source | Bronze | Silver | Read by |
|---|---|---|---|
| [public.actor](../source/tables/public.actor.md) | `bronze_public.actor` | [public__actor](../target/silver/tables/public__actor.md) |  |
| [public.address](../source/tables/public.address.md) | `bronze_public.address` | [public__address](../target/silver/tables/public__address.md) |  |
| [public.category](../source/tables/public.category.md) | `bronze_public.category` | [public__category](../target/silver/tables/public__category.md) |  |
| [public.city](../source/tables/public.city.md) | `bronze_public.city` | [public__city](../target/silver/tables/public__city.md) |  |
| [public.country](../source/tables/public.country.md) | `bronze_public.country` | [public__country](../target/silver/tables/public__country.md) |  |
| [public.customer](../source/tables/public.customer.md) | `bronze_public.customer` | [public__customer](../target/silver/tables/public__customer.md) |  |
| [public.film](../source/tables/public.film.md) | `bronze_public.film` | [public__film](../target/silver/tables/public__film.md) |  |
| [public.film_actor](../source/tables/public.film_actor.md) | `bronze_public.film_actor` | [public__film_actor](../target/silver/tables/public__film_actor.md) |  |
| [public.film_category](../source/tables/public.film_category.md) | `bronze_public.film_category` | [public__film_category](../target/silver/tables/public__film_category.md) |  |
| [public.film_embedding](../source/tables/public.film_embedding.md) | `bronze_public.film_embedding` | [public__film_embedding](../target/silver/tables/public__film_embedding.md) |  |
| [public.inventory](../source/tables/public.inventory.md) | `bronze_public.inventory` | [public__inventory](../target/silver/tables/public__inventory.md) |  |
| [public.language](../source/tables/public.language.md) | `bronze_public.language` | [public__language](../target/silver/tables/public__language.md) |  |
| [public.payment](../source/tables/public.payment.md) | `bronze_public.payment` | [public__payment](../target/silver/tables/public__payment.md) |  |
| [public.rental](../source/tables/public.rental.md) | `bronze_public.rental` | [public__rental](../target/silver/tables/public__rental.md) |  |
| [public.staff](../source/tables/public.staff.md) | `bronze_public.staff` | [public__staff](../target/silver/tables/public__staff.md) |  |
| [public.store](../source/tables/public.store.md) | `bronze_public.store` | [public__store](../target/silver/tables/public__store.md) |  |

## How lineage is derived

- **source → bronze:** the deployed plan's column mapping (`expr`, lossiness).
- **bronze → silver → gold:** the dbt SQL parsed in Trino's dialect (sqlglot), `select *` expanded with upstream columns.
- Edges marked _by name_ were matched on column names because the SQL did not parse.
