---
title: "SLAs and data contracts"
order: 82
ekos_generated: true
---

# SLAs and data contracts

## Service levels

<!-- ekos:manual id="sla" -->
_Freshness targets per layer, availability window, support hours, RPO/RTO (Iceberg snapshots retain history until expiry)._
<!-- /ekos:manual -->

## Data contracts (generated)

What each silver table guarantees to its consumers, derived from the source constraints it is tested against. A change that would break a contract arrives as a proposal, not as a silent change.

### [public__actor](../target/silver/tables/public__actor.md)

```yaml
relation: silver_public.actor
source: public.actor
grain: ['actor_id']
refresh: 0 * * * * (full)
not_null: ['actor_id', 'first_name', 'last_name', 'last_update']
schema_change_policy: additive changes automatic; breaking changes by approved proposal
```

### [public__address](../target/silver/tables/public__address.md)

```yaml
relation: silver_public.address
source: public.address
grain: ['address_id']
refresh: 0 * * * * (full)
not_null: ['address_id', 'address', 'district', 'city_id', 'phone', 'last_update']
references: ['relationships → public__city.city_id']
schema_change_policy: additive changes automatic; breaking changes by approved proposal
```

### [public__category](../target/silver/tables/public__category.md)

```yaml
relation: silver_public.category
source: public.category
grain: ['category_id']
refresh: 0 * * * * (full)
not_null: ['category_id', 'name', 'last_update']
schema_change_policy: additive changes automatic; breaking changes by approved proposal
```

### [public__city](../target/silver/tables/public__city.md)

```yaml
relation: silver_public.city
source: public.city
grain: ['city_id']
refresh: 0 * * * * (full)
not_null: ['city_id', 'city', 'country_id', 'last_update']
references: ['relationships → public__country.country_id']
schema_change_policy: additive changes automatic; breaking changes by approved proposal
```

### [public__country](../target/silver/tables/public__country.md)

```yaml
relation: silver_public.country
source: public.country
grain: ['country_id']
refresh: 0 * * * * (full)
not_null: ['country_id', 'country', 'last_update']
schema_change_policy: additive changes automatic; breaking changes by approved proposal
```

### [public__customer](../target/silver/tables/public__customer.md)

```yaml
relation: silver_public.customer
source: public.customer
grain: ['customer_id']
refresh: 0 * * * * (incremental)
not_null: ['customer_id', 'store_id', 'first_name', 'last_name', 'address_id', 'activebool', 'create_date', 'uuid']
references: ['relationships → public__store.store_id', 'relationships → public__address.address_id']
schema_change_policy: additive changes automatic; breaking changes by approved proposal
```

### [public__film](../target/silver/tables/public__film.md)

```yaml
relation: silver_public.film
source: public.film
grain: ['film_id']
refresh: 0 * * * * (incremental)
not_null: ['film_id', 'title', 'language_id', 'rental_duration', 'rental_rate', 'replacement_cost', 'last_update', 'fulltext']
references: ['relationships → public__language.language_id', 'relationships → public__language.language_id']
accepted_values: ["rating ∈ ['G', 'PG', 'PG-13', 'R', 'NC-17']"]
schema_change_policy: additive changes automatic; breaking changes by approved proposal
```

### [public__film_actor](../target/silver/tables/public__film_actor.md)

```yaml
relation: silver_public.film_actor
source: public.film_actor
grain: ['actor_id', 'film_id']
refresh: 0 * * * * (full)
not_null: ['actor_id', 'film_id', 'last_update']
references: ['relationships → public__actor.actor_id', 'relationships → public__film.film_id']
schema_change_policy: additive changes automatic; breaking changes by approved proposal
```

### [public__film_category](../target/silver/tables/public__film_category.md)

```yaml
relation: silver_public.film_category
source: public.film_category
grain: ['film_id', 'category_id']
refresh: 0 * * * * (full)
not_null: ['film_id', 'category_id', 'last_update']
references: ['relationships → public__film.film_id', 'relationships → public__category.category_id']
schema_change_policy: additive changes automatic; breaking changes by approved proposal
```

### [public__film_embedding](../target/silver/tables/public__film_embedding.md)

```yaml
relation: silver_public.film_embedding
source: public.film_embedding
grain: ['film_id']
refresh: 0 * * * * (full)
not_null: ['film_id', 'embedding', 'last_update']
references: ['relationships → public__film.film_id']
schema_change_policy: additive changes automatic; breaking changes by approved proposal
```

### [public__inventory](../target/silver/tables/public__inventory.md)

```yaml
relation: silver_public.inventory
source: public.inventory
grain: ['inventory_id']
refresh: 0 * * * * (incremental)
not_null: ['inventory_id', 'film_id', 'store_id', 'last_update']
references: ['relationships → public__film.film_id', 'relationships → public__store.store_id']
schema_change_policy: additive changes automatic; breaking changes by approved proposal
```

### [public__language](../target/silver/tables/public__language.md)

```yaml
relation: silver_public.language
source: public.language
grain: ['language_id']
refresh: 0 * * * * (full)
not_null: ['language_id', 'name', 'last_update']
schema_change_policy: additive changes automatic; breaking changes by approved proposal
```

### [public__payment](../target/silver/tables/public__payment.md)

```yaml
relation: silver_public.payment
source: public.payment
grain: ['payment_date', 'payment_id']
refresh: 0 * * * * (full)
not_null: ['payment_id', 'customer_id', 'staff_id', 'rental_id', 'amount', 'payment_date', 'uuid']
schema_change_policy: additive changes automatic; breaking changes by approved proposal
```

### [public__rental](../target/silver/tables/public__rental.md)

```yaml
relation: silver_public.rental
source: public.rental
grain: ['rental_id']
refresh: 0 * * * * (incremental)
not_null: ['rental_id', 'rented_at', 'inventory_id', 'customer_id', 'staff_id', 'last_update', 'uuid']
references: ['relationships → public__inventory.inventory_id', 'relationships → public__customer.customer_id', 'relationships → public__staff.staff_id']
schema_change_policy: additive changes automatic; breaking changes by approved proposal
```

### [public__staff](../target/silver/tables/public__staff.md)

```yaml
relation: silver_public.staff
source: public.staff
grain: ['staff_id']
refresh: 0 * * * * (full)
not_null: ['staff_id', 'first_name', 'last_name', 'address_id', 'store_id', 'active', 'username', 'last_update']
references: ['relationships → public__address.address_id', 'relationships → public__store.store_id']
schema_change_policy: additive changes automatic; breaking changes by approved proposal
```

### [public__store](../target/silver/tables/public__store.md)

```yaml
relation: silver_public.store
source: public.store
grain: ['store_id']
refresh: 0 * * * * (full)
not_null: ['store_id', 'manager_staff_id', 'address_id', 'last_update']
references: ['relationships → public__address.address_id']
schema_change_policy: additive changes automatic; breaking changes by approved proposal
```
