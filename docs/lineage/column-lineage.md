---
title: "Column lineage (STTM)"
order: 51
ekos_generated: true
---

# Column lineage (STTM)

Source-to-target mapping (STTM): one row per source column, through bronze and silver, with every gold column it reaches.

## [public.actor](../source/tables/public.actor.md)

| Source column | Source type | Bronze type | Bronze mapping | Silver column | Silver transform | Gold columns |
|---|---|---|---|---|---|---|
| `actor_id` | `integer` | `integer` | pass-through | `public__actor.actor_id` | pass-through |  |
| `first_name` | `text` | `varchar` | pass-through | `public__actor.first_name` | pass-through |  |
| `last_name` | `text` | `varchar` | pass-through | `public__actor.last_name` | pass-through |  |
| `last_update` | `timestamp with time zone` | `timestamp(6) with time zone` | `CAST("last_update" AS timestamp(6) with time zone)` | `public__actor.last_update` | pass-through |  |

## [public.address](../source/tables/public.address.md)

| Source column | Source type | Bronze type | Bronze mapping | Silver column | Silver transform | Gold columns |
|---|---|---|---|---|---|---|
| `address_id` | `integer` | `integer` | pass-through | `public__address.address_id` | pass-through |  |
| `address` | `text` | `varchar` | pass-through | `public__address.address` | pass-through |  |
| `address2` | `text` | `varchar` | pass-through | `public__address.address2` | pass-through |  |
| `district` | `text` | `varchar` | pass-through | `public__address.district` | pass-through |  |
| `city_id` | `integer` | `integer` | pass-through | `public__address.city_id` | pass-through |  |
| `postal_code` | `text` | `varchar` | pass-through | `public__address.postal_code` | pass-through |  |
| `phone` | `text` | `varchar` | pass-through | `public__address.phone` | pass-through |  |
| `last_update` | `timestamp with time zone` | `timestamp(6) with time zone` | `CAST("last_update" AS timestamp(6) with time zone)` | `public__address.last_update` | pass-through |  |

## [public.category](../source/tables/public.category.md)

| Source column | Source type | Bronze type | Bronze mapping | Silver column | Silver transform | Gold columns |
|---|---|---|---|---|---|---|
| `category_id` | `integer` | `integer` | pass-through | `public__category.category_id` | pass-through |  |
| `name` | `text` | `varchar` | pass-through | `public__category.name` | pass-through |  |
| `last_update` | `timestamp with time zone` | `timestamp(6) with time zone` | `CAST("last_update" AS timestamp(6) with time zone)` | `public__category.last_update` | pass-through |  |

## [public.city](../source/tables/public.city.md)

| Source column | Source type | Bronze type | Bronze mapping | Silver column | Silver transform | Gold columns |
|---|---|---|---|---|---|---|
| `city_id` | `integer` | `integer` | pass-through | `public__city.city_id` | pass-through |  |
| `city` | `text` | `varchar` | pass-through | `public__city.city` | pass-through |  |
| `country_id` | `integer` | `integer` | pass-through | `public__city.country_id` | pass-through |  |
| `last_update` | `timestamp with time zone` | `timestamp(6) with time zone` | `CAST("last_update" AS timestamp(6) with time zone)` | `public__city.last_update` | pass-through |  |

## [public.country](../source/tables/public.country.md)

| Source column | Source type | Bronze type | Bronze mapping | Silver column | Silver transform | Gold columns |
|---|---|---|---|---|---|---|
| `country_id` | `integer` | `integer` | pass-through | `public__country.country_id` | pass-through |  |
| `country` | `text` | `varchar` | pass-through | `public__country.country` | pass-through |  |
| `last_update` | `timestamp with time zone` | `timestamp(6) with time zone` | `CAST("last_update" AS timestamp(6) with time zone)` | `public__country.last_update` | pass-through |  |

## [public.customer](../source/tables/public.customer.md)

| Source column | Source type | Bronze type | Bronze mapping | Silver column | Silver transform | Gold columns |
|---|---|---|---|---|---|---|
| `customer_id` | `integer` | `integer` | pass-through | `public__customer.customer_id` | pass-through |  |
| `store_id` | `integer` | `integer` | pass-through | `public__customer.store_id` | pass-through |  |
| `first_name` | `text` | `varchar` | pass-through | `public__customer.first_name` | pass-through |  |
| `last_name` | `text` | `varchar` | pass-through | `public__customer.last_name` | pass-through |  |
| `email` | `text` | `varchar` | pass-through | `public__customer.email` | pass-through |  |
| `address_id` | `integer` | `integer` | pass-through | `public__customer.address_id` | pass-through |  |
| `activebool` | `boolean` | `boolean` | pass-through | `public__customer.activebool` | pass-through |  |
| `create_date` | `date` | `date` | pass-through | `public__customer.create_date` | pass-through |  |
| `last_update` | `timestamp with time zone` | `timestamp(6) with time zone` | `CAST("last_update" AS timestamp(6) with time zone)` | `public__customer.last_update` | pass-through |  |
| `active` | `integer` | `integer` | pass-through | `public__customer.active` | pass-through |  |
| `uuid` | `uuid` | `uuid` | pass-through | `public__customer.uuid` | pass-through |  |
| `loyalty_tier` | `text` | `varchar` | pass-through | `public__customer.loyalty_tier` | pass-through |  |

## [public.film](../source/tables/public.film.md)

| Source column | Source type | Bronze type | Bronze mapping | Silver column | Silver transform | Gold columns |
|---|---|---|---|---|---|---|
| `film_id` | `integer` | `integer` | pass-through | `public__film.film_id` | pass-through |  |
| `title` | `text` | `varchar` | pass-through | `public__film.title` | pass-through |  |
| `description` | `text` | `varchar` | pass-through | `public__film.description` | pass-through |  |
| `release_year` | `year` | `integer` | `CAST("release_year" AS integer)` | `public__film.release_year` | pass-through |  |
| `language_id` | `integer` | `integer` | pass-through | `public__film.language_id` | pass-through |  |
| `original_language_id` | `integer` | `integer` | pass-through | `public__film.original_language_id` | pass-through |  |
| `rental_duration` | `smallint` | `integer` | `CAST("rental_duration" AS integer)` [widening] | `public__film.rental_duration` | pass-through |  |
| `rental_rate` | `numeric(4,2)` | `decimal(4,2)` | pass-through | `public__film.rental_rate` | pass-through |  |
| `length` | `smallint` | `integer` | `CAST("length" AS integer)` [widening] | `public__film.length` | pass-through |  |
| `replacement_cost` | `numeric(5,2)` | `decimal(5,2)` | pass-through | `public__film.replacement_cost` | pass-through |  |
| `rating` | `mpaa_rating` | `varchar` | pass-through | `public__film.rating` | pass-through |  |
| `last_update` | `timestamp with time zone` | `timestamp(6) with time zone` | `CAST("last_update" AS timestamp(6) with time zone)` | `public__film.last_update` | pass-through |  |
| `special_features` | `text[]` | `array(varchar)` | `CAST("special_features" AS array(varchar))` | `public__film.special_features` | pass-through |  |
| `fulltext` | `tsvector` | `varchar` | pass-through [as_text] | `public__film.fulltext` | pass-through |  |
| `length_hours` | `numeric(4,2)` | `decimal(4,2)` | pass-through | `public__film.length_hours` | pass-through |  |

## [public.film_actor](../source/tables/public.film_actor.md)

| Source column | Source type | Bronze type | Bronze mapping | Silver column | Silver transform | Gold columns |
|---|---|---|---|---|---|---|
| `actor_id` | `integer` | `integer` | pass-through | `public__film_actor.actor_id` | pass-through |  |
| `film_id` | `integer` | `integer` | pass-through | `public__film_actor.film_id` | pass-through |  |
| `last_update` | `timestamp with time zone` | `timestamp(6) with time zone` | `CAST("last_update" AS timestamp(6) with time zone)` | `public__film_actor.last_update` | pass-through |  |

## [public.film_category](../source/tables/public.film_category.md)

| Source column | Source type | Bronze type | Bronze mapping | Silver column | Silver transform | Gold columns |
|---|---|---|---|---|---|---|
| `film_id` | `integer` | `integer` | pass-through | `public__film_category.film_id` | pass-through |  |
| `category_id` | `integer` | `integer` | pass-through | `public__film_category.category_id` | pass-through |  |
| `last_update` | `timestamp with time zone` | `timestamp(6) with time zone` | `CAST("last_update" AS timestamp(6) with time zone)` | `public__film_category.last_update` | pass-through |  |

## [public.film_embedding](../source/tables/public.film_embedding.md)

| Source column | Source type | Bronze type | Bronze mapping | Silver column | Silver transform | Gold columns |
|---|---|---|---|---|---|---|
| `film_id` | `integer` | `integer` | pass-through | `public__film_embedding.film_id` | pass-through |  |
| `embedding` | `vector(20)` | `array(real)` | pass-through | `public__film_embedding.embedding` | pass-through |  |
| `last_update` | `timestamp with time zone` | `timestamp(6) with time zone` | `CAST("last_update" AS timestamp(6) with time zone)` | `public__film_embedding.last_update` | pass-through |  |

## [public.inventory](../source/tables/public.inventory.md)

| Source column | Source type | Bronze type | Bronze mapping | Silver column | Silver transform | Gold columns |
|---|---|---|---|---|---|---|
| `inventory_id` | `integer` | `integer` | pass-through | `public__inventory.inventory_id` | pass-through |  |
| `film_id` | `integer` | `integer` | pass-through | `public__inventory.film_id` | pass-through |  |
| `store_id` | `integer` | `integer` | pass-through | `public__inventory.store_id` | pass-through |  |
| `last_update` | `timestamp with time zone` | `timestamp(6) with time zone` | `CAST("last_update" AS timestamp(6) with time zone)` | `public__inventory.last_update` | pass-through |  |

## [public.language](../source/tables/public.language.md)

| Source column | Source type | Bronze type | Bronze mapping | Silver column | Silver transform | Gold columns |
|---|---|---|---|---|---|---|
| `language_id` | `integer` | `integer` | pass-through | `public__language.language_id` | pass-through |  |
| `name` | `text` | `varchar` | pass-through | `public__language.name` | pass-through |  |
| `last_update` | `timestamp with time zone` | `timestamp(6) with time zone` | `CAST("last_update" AS timestamp(6) with time zone)` | `public__language.last_update` | pass-through |  |

## [public.payment](../source/tables/public.payment.md)

| Source column | Source type | Bronze type | Bronze mapping | Silver column | Silver transform | Gold columns |
|---|---|---|---|---|---|---|
| `payment_id` | `integer` | `integer` | pass-through | `public__payment.payment_id` | pass-through |  |
| `customer_id` | `integer` | `integer` | pass-through | `public__payment.customer_id` | pass-through |  |
| `staff_id` | `integer` | `integer` | pass-through | `public__payment.staff_id` | pass-through |  |
| `rental_id` | `integer` | `integer` | pass-through | `public__payment.rental_id` | pass-through |  |
| `amount` | `numeric(5,2)` | `decimal(5,2)` | pass-through | `public__payment.amount` | pass-through |  |
| `payment_date` | `timestamp with time zone` | `timestamp(6) with time zone` | `CAST("payment_date" AS timestamp(6) with time zone)` | `public__payment.payment_date` | pass-through |  |
| `uuid` | `uuid` | `uuid` | pass-through | `public__payment.uuid` | pass-through |  |

## [public.rental](../source/tables/public.rental.md)

| Source column | Source type | Bronze type | Bronze mapping | Silver column | Silver transform | Gold columns |
|---|---|---|---|---|---|---|
| `rental_id` | `integer` | `integer` | pass-through | `public__rental.rental_id` | pass-through |  |
| `rented_at` | `timestamp with time zone` | `timestamp(6) with time zone` | `CAST("rented_at" AS timestamp(6) with time zone)` | `public__rental.rented_at` | pass-through |  |
| `inventory_id` | `integer` | `integer` | pass-through | `public__rental.inventory_id` | pass-through |  |
| `customer_id` | `integer` | `integer` | pass-through | `public__rental.customer_id` | pass-through |  |
| `return_date` | `timestamp with time zone` | `timestamp(6) with time zone` | `CAST("return_date" AS timestamp(6) with time zone)` | `public__rental.return_date` | pass-through |  |
| `staff_id` | `integer` | `integer` | pass-through | `public__rental.staff_id` | pass-through |  |
| `last_update` | `timestamp with time zone` | `timestamp(6) with time zone` | `CAST("last_update" AS timestamp(6) with time zone)` | `public__rental.last_update` | pass-through |  |
| `uuid` | `uuid` | `uuid` | pass-through | `public__rental.uuid` | pass-through |  |

## [public.staff](../source/tables/public.staff.md)

| Source column | Source type | Bronze type | Bronze mapping | Silver column | Silver transform | Gold columns |
|---|---|---|---|---|---|---|
| `staff_id` | `integer` | `integer` | pass-through | `public__staff.staff_id` | pass-through |  |
| `first_name` | `text` | `varchar` | pass-through | `public__staff.first_name` | pass-through |  |
| `last_name` | `text` | `varchar` | pass-through | `public__staff.last_name` | pass-through |  |
| `address_id` | `integer` | `integer` | pass-through | `public__staff.address_id` | pass-through |  |
| `email` | `text` | `varchar` | pass-through | `public__staff.email` | pass-through |  |
| `store_id` | `integer` | `integer` | pass-through | `public__staff.store_id` | pass-through |  |
| `active` | `boolean` | `boolean` | pass-through | `public__staff.active` | pass-through |  |
| `username` | `text` | `varchar` | pass-through | `public__staff.username` | pass-through |  |
| `password` | `text` | `varchar` | pass-through | `public__staff.password` | pass-through |  |
| `last_update` | `timestamp with time zone` | `timestamp(6) with time zone` | `CAST("last_update" AS timestamp(6) with time zone)` | `public__staff.last_update` | pass-through |  |
| `picture` | `bytea` | `varbinary` | pass-through | `public__staff.picture` | pass-through |  |

## [public.store](../source/tables/public.store.md)

| Source column | Source type | Bronze type | Bronze mapping | Silver column | Silver transform | Gold columns |
|---|---|---|---|---|---|---|
| `store_id` | `integer` | `integer` | pass-through | `public__store.store_id` | pass-through |  |
| `manager_staff_id` | `integer` | `integer` | pass-through | `public__store.manager_staff_id` | pass-through |  |
| `address_id` | `integer` | `integer` | pass-through | `public__store.address_id` | pass-through |  |
| `last_update` | `timestamp with time zone` | `timestamp(6) with time zone` | `CAST("last_update" AS timestamp(6) with time zone)` | `public__store.last_update` | pass-through |  |
