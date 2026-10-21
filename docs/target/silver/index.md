---
title: "Silver"
order: 42
ekos_generated: true
---

# Silver

Clean, conformed, tested: one model per bronze table, generated from source facts (RFC 0193). Latest version per key, deletes removed, approved PII masked. [ER diagram](../../target/silver/er-diagram.md)

| Model | Relation | Source | Columns | Tests | History | Masked | Health |
|---|---|---|---|---|---|---|---|
| [public__actor](../../target/silver/tables/public__actor.md) | `silver_public.actor` | [public.actor](../../source/tables/public.actor.md) | 4 | 5 |  |  | ✅ healthy |
| [public__address](../../target/silver/tables/public__address.md) | `silver_public.address` | [public.address](../../source/tables/public.address.md) | 8 | 8 |  |  | ✅ healthy |
| [public__category](../../target/silver/tables/public__category.md) | `silver_public.category` | [public.category](../../source/tables/public.category.md) | 3 | 4 |  |  | ✅ healthy |
| [public__city](../../target/silver/tables/public__city.md) | `silver_public.city` | [public.city](../../source/tables/public.city.md) | 4 | 6 |  |  | ✅ healthy |
| [public__country](../../target/silver/tables/public__country.md) | `silver_public.country` | [public.country](../../source/tables/public.country.md) | 3 | 4 |  |  | ✅ healthy |
| [public__customer](../../target/silver/tables/public__customer.md) | `silver_public.customer` | [public.customer](../../source/tables/public.customer.md) | 12 | 11 |  |  | ✅ healthy |
| [public__film](../../target/silver/tables/public__film.md) | `silver_public.film` | [public.film](../../source/tables/public.film.md) | 15 | 12 |  |  | ✅ healthy |
| [public__film_actor](../../target/silver/tables/public__film_actor.md) | `silver_public.film_actor` | [public.film_actor](../../source/tables/public.film_actor.md) | 3 | 6 |  |  | ✅ healthy |
| [public__film_category](../../target/silver/tables/public__film_category.md) | `silver_public.film_category` | [public.film_category](../../source/tables/public.film_category.md) | 3 | 6 |  |  | ✅ healthy |
| [public__film_embedding](../../target/silver/tables/public__film_embedding.md) | `silver_public.film_embedding` | [public.film_embedding](../../source/tables/public.film_embedding.md) | 3 | 5 |  |  | ✅ healthy |
| [public__inventory](../../target/silver/tables/public__inventory.md) | `silver_public.inventory` | [public.inventory](../../source/tables/public.inventory.md) | 4 | 7 |  |  | ✅ healthy |
| [public__language](../../target/silver/tables/public__language.md) | `silver_public.language` | [public.language](../../source/tables/public.language.md) | 3 | 4 |  |  | ✅ healthy |
| [public__payment](../../target/silver/tables/public__payment.md) | `silver_public.payment` | [public.payment](../../source/tables/public.payment.md) | 7 | 8 |  |  | ✅ healthy |
| [public__rental](../../target/silver/tables/public__rental.md) | `silver_public.rental` | [public.rental](../../source/tables/public.rental.md) | 8 | 11 |  |  | ✅ healthy |
| [public__staff](../../target/silver/tables/public__staff.md) | `silver_public.staff` | [public.staff](../../source/tables/public.staff.md) | 11 | 11 |  |  | ✅ healthy |
| [public__store](../../target/silver/tables/public__store.md) | `silver_public.store` | [public.store](../../source/tables/public.store.md) | 4 | 6 |  |  | ✅ healthy |
