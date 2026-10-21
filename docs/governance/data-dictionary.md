---
title: "Data dictionary"
order: 71
ekos_generated: true
---

# Data dictionary

Business-facing columns: silver (conformed entities) and gold (marts). Descriptions come from source comments and mart definitions.

## [public__actor](../target/silver/tables/public__actor.md) (silver)

| Column | Type | Description | Nullability | Source | PII |
|---|---|---|---|---|---|
| `actor_id` | `integer` |  | required | public.actor.actor_id |  |
| `first_name` | `varchar` |  | required | public.actor.first_name | personname ⚠️ unmasked |
| `last_name` | `varchar` |  | required | public.actor.last_name | personname ⚠️ unmasked |
| `last_update` | `timestamp(6) with time zone` |  | required | public.actor.last_update |  |

## [public__address](../target/silver/tables/public__address.md) (silver)

| Column | Type | Description | Nullability | Source | PII |
|---|---|---|---|---|---|
| `address_id` | `integer` |  | required | public.address.address_id | postaladdress ⚠️ unmasked |
| `address` | `varchar` |  | required | public.address.address | postaladdress ⚠️ unmasked |
| `address2` | `varchar` |  |  | public.address.address2 | postaladdress ⚠️ unmasked |
| `district` | `varchar` |  | required | public.address.district |  |
| `city_id` | `integer` |  | required | public.address.city_id |  |
| `postal_code` | `varchar` |  |  | public.address.postal_code | postaladdress ⚠️ unmasked |
| `phone` | `varchar` |  | required | public.address.phone | phone ⚠️ unmasked |
| `last_update` | `timestamp(6) with time zone` |  | required | public.address.last_update |  |

## [public__category](../target/silver/tables/public__category.md) (silver)

| Column | Type | Description | Nullability | Source | PII |
|---|---|---|---|---|---|
| `category_id` | `integer` |  | required | public.category.category_id |  |
| `name` | `varchar` |  | required | public.category.name |  |
| `last_update` | `timestamp(6) with time zone` |  | required | public.category.last_update |  |

## [public__city](../target/silver/tables/public__city.md) (silver)

| Column | Type | Description | Nullability | Source | PII |
|---|---|---|---|---|---|
| `city_id` | `integer` |  | required | public.city.city_id |  |
| `city` | `varchar` |  | required | public.city.city |  |
| `country_id` | `integer` |  | required | public.city.country_id |  |
| `last_update` | `timestamp(6) with time zone` |  | required | public.city.last_update |  |

## [public__country](../target/silver/tables/public__country.md) (silver)

| Column | Type | Description | Nullability | Source | PII |
|---|---|---|---|---|---|
| `country_id` | `integer` |  | required | public.country.country_id |  |
| `country` | `varchar` |  | required | public.country.country |  |
| `last_update` | `timestamp(6) with time zone` |  | required | public.country.last_update |  |

## [public__customer](../target/silver/tables/public__customer.md) (silver)

| Column | Type | Description | Nullability | Source | PII |
|---|---|---|---|---|---|
| `customer_id` | `integer` |  | required | public.customer.customer_id |  |
| `store_id` | `integer` |  | required | public.customer.store_id |  |
| `first_name` | `varchar` |  | required | public.customer.first_name | personname ⚠️ unmasked |
| `last_name` | `varchar` |  | required | public.customer.last_name | personname ⚠️ unmasked |
| `email` | `varchar` |  |  | public.customer.email | email ⚠️ unmasked |
| `address_id` | `integer` |  | required | public.customer.address_id | postaladdress ⚠️ unmasked |
| `activebool` | `boolean` |  | required | public.customer.activebool |  |
| `create_date` | `date` |  | required | public.customer.create_date |  |
| `last_update` | `timestamp(6) with time zone` |  |  | public.customer.last_update |  |
| `active` | `integer` |  |  | public.customer.active |  |
| `uuid` | `uuid` |  | required | public.customer.uuid |  |
| `loyalty_tier` | `varchar` |  |  | public.customer.loyalty_tier |  |

## [public__film](../target/silver/tables/public__film.md) (silver)

| Column | Type | Description | Nullability | Source | PII |
|---|---|---|---|---|---|
| `film_id` | `integer` |  | required | public.film.film_id |  |
| `title` | `varchar` |  | required | public.film.title |  |
| `description` | `varchar` |  |  | public.film.description |  |
| `release_year` | `integer` |  |  | public.film.release_year |  |
| `language_id` | `integer` |  | required | public.film.language_id |  |
| `original_language_id` | `integer` |  |  | public.film.original_language_id |  |
| `rental_duration` | `integer` |  | required | public.film.rental_duration |  |
| `rental_rate` | `decimal(4,2)` |  | required | public.film.rental_rate |  |
| `length` | `integer` |  |  | public.film.length |  |
| `replacement_cost` | `decimal(5,2)` |  | required | public.film.replacement_cost |  |
| `rating` | `varchar` |  |  | public.film.rating |  |
| `last_update` | `timestamp(6) with time zone` |  | required | public.film.last_update |  |
| `special_features` | `array(varchar)` |  |  | public.film.special_features |  |
| `fulltext` | `varchar` |  | required | public.film.fulltext |  |
| `length_hours` | `decimal(4,2)` |  |  | public.film.length_hours |  |

## [public__film_actor](../target/silver/tables/public__film_actor.md) (silver)

| Column | Type | Description | Nullability | Source | PII |
|---|---|---|---|---|---|
| `actor_id` | `integer` |  | required | public.film_actor.actor_id |  |
| `film_id` | `integer` |  | required | public.film_actor.film_id |  |
| `last_update` | `timestamp(6) with time zone` |  | required | public.film_actor.last_update |  |

## [public__film_category](../target/silver/tables/public__film_category.md) (silver)

| Column | Type | Description | Nullability | Source | PII |
|---|---|---|---|---|---|
| `film_id` | `integer` |  | required | public.film_category.film_id |  |
| `category_id` | `integer` |  | required | public.film_category.category_id |  |
| `last_update` | `timestamp(6) with time zone` |  | required | public.film_category.last_update |  |

## [public__film_embedding](../target/silver/tables/public__film_embedding.md) (silver)

| Column | Type | Description | Nullability | Source | PII |
|---|---|---|---|---|---|
| `film_id` | `integer` |  | required | public.film_embedding.film_id |  |
| `embedding` | `array(real)` |  | required | public.film_embedding.embedding |  |
| `last_update` | `timestamp(6) with time zone` |  | required | public.film_embedding.last_update |  |

## [public__inventory](../target/silver/tables/public__inventory.md) (silver)

| Column | Type | Description | Nullability | Source | PII |
|---|---|---|---|---|---|
| `inventory_id` | `integer` |  | required | public.inventory.inventory_id |  |
| `film_id` | `integer` |  | required | public.inventory.film_id |  |
| `store_id` | `integer` |  | required | public.inventory.store_id |  |
| `last_update` | `timestamp(6) with time zone` |  | required | public.inventory.last_update |  |

## [public__language](../target/silver/tables/public__language.md) (silver)

| Column | Type | Description | Nullability | Source | PII |
|---|---|---|---|---|---|
| `language_id` | `integer` |  | required | public.language.language_id |  |
| `name` | `varchar` |  | required | public.language.name |  |
| `last_update` | `timestamp(6) with time zone` |  | required | public.language.last_update |  |

## [public__payment](../target/silver/tables/public__payment.md) (silver)

| Column | Type | Description | Nullability | Source | PII |
|---|---|---|---|---|---|
| `payment_id` | `integer` |  | required | public.payment.payment_id |  |
| `customer_id` | `integer` |  | required | public.payment.customer_id |  |
| `staff_id` | `integer` |  | required | public.payment.staff_id |  |
| `rental_id` | `integer` |  | required | public.payment.rental_id |  |
| `amount` | `decimal(5,2)` |  | required | public.payment.amount |  |
| `payment_date` | `timestamp(6) with time zone` |  | required | public.payment.payment_date |  |
| `uuid` | `uuid` |  | required | public.payment.uuid |  |

## [public__rental](../target/silver/tables/public__rental.md) (silver)

| Column | Type | Description | Nullability | Source | PII |
|---|---|---|---|---|---|
| `rental_id` | `integer` |  | required | public.rental.rental_id |  |
| `rented_at` | `timestamp(6) with time zone` |  | required | public.rental.rented_at |  |
| `inventory_id` | `integer` |  | required | public.rental.inventory_id |  |
| `customer_id` | `integer` |  | required | public.rental.customer_id |  |
| `return_date` | `timestamp(6) with time zone` |  |  | public.rental.return_date |  |
| `staff_id` | `integer` |  | required | public.rental.staff_id |  |
| `last_update` | `timestamp(6) with time zone` |  | required | public.rental.last_update |  |
| `uuid` | `uuid` |  | required | public.rental.uuid |  |

## [public__staff](../target/silver/tables/public__staff.md) (silver)

| Column | Type | Description | Nullability | Source | PII |
|---|---|---|---|---|---|
| `staff_id` | `integer` |  | required | public.staff.staff_id |  |
| `first_name` | `varchar` |  | required | public.staff.first_name | personname ⚠️ unmasked |
| `last_name` | `varchar` |  | required | public.staff.last_name | personname ⚠️ unmasked |
| `address_id` | `integer` |  | required | public.staff.address_id | postaladdress ⚠️ unmasked |
| `email` | `varchar` |  |  | public.staff.email | email ⚠️ unmasked |
| `store_id` | `integer` |  | required | public.staff.store_id |  |
| `active` | `boolean` |  | required | public.staff.active |  |
| `username` | `varchar` |  | required | public.staff.username |  |
| `password` | `varchar` |  |  | public.staff.password | credential ⚠️ unmasked |
| `last_update` | `timestamp(6) with time zone` |  | required | public.staff.last_update |  |
| `picture` | `varbinary` |  |  | public.staff.picture |  |

## [public__store](../target/silver/tables/public__store.md) (silver)

| Column | Type | Description | Nullability | Source | PII |
|---|---|---|---|---|---|
| `store_id` | `integer` |  | required | public.store.store_id |  |
| `manager_staff_id` | `integer` |  | required | public.store.manager_staff_id |  |
| `address_id` | `integer` |  | required | public.store.address_id | postaladdress ⚠️ unmasked |
| `last_update` | `timestamp(6) with time zone` |  | required | public.store.last_update |  |
