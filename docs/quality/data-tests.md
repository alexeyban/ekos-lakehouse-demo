---
title: "Data quality tests"
order: 62
ekos_generated: true
---

# Data quality tests

> Evidence collected 2026-10-21 15:32 UTC at pipeline commit `efeeffd`.

Every data-quality rule, the fact it comes from and its last result. Rules are generated: a primary key becomes `unique` + `not_null`, a NOT NULL column `not_null`, a declared foreign key `relationships`, an enum `accepted_values`; gold marts get grain uniqueness and measure reconciliation.

## Rule catalogue

| Rule | Tests |
|---|---|
| enum-labels | 1 |
| foreign-key | 19 |
| not-null | 78 |
| primary-key | 16 |

## Coverage

| Model | Layer | Tests | Key | Not null | Relationships | Documented columns |
|---|---|---|---|---|---|---|
| [public__actor](../target/silver/tables/public__actor.md) | silver | 5 | ✅ | ✅ | — | 0/4 |
| [public__address](../target/silver/tables/public__address.md) | silver | 8 | ✅ | ✅ | ✅ | 0/8 |
| [public__category](../target/silver/tables/public__category.md) | silver | 4 | ✅ | ✅ | — | 0/3 |
| [public__city](../target/silver/tables/public__city.md) | silver | 6 | ✅ | ✅ | ✅ | 0/4 |
| [public__country](../target/silver/tables/public__country.md) | silver | 4 | ✅ | ✅ | — | 0/3 |
| [public__customer](../target/silver/tables/public__customer.md) | silver | 11 | ✅ | ✅ | ✅ | 0/12 |
| [public__film](../target/silver/tables/public__film.md) | silver | 12 | ✅ | ✅ | ✅ | 0/15 |
| [public__film_actor](../target/silver/tables/public__film_actor.md) | silver | 6 | ✅ | ✅ | ✅ | 0/3 |
| [public__film_category](../target/silver/tables/public__film_category.md) | silver | 6 | ✅ | ✅ | ✅ | 0/3 |
| [public__film_embedding](../target/silver/tables/public__film_embedding.md) | silver | 5 | ✅ | ✅ | ✅ | 0/3 |
| [public__inventory](../target/silver/tables/public__inventory.md) | silver | 7 | ✅ | ✅ | ✅ | 0/4 |
| [public__language](../target/silver/tables/public__language.md) | silver | 4 | ✅ | ✅ | — | 0/3 |
| [public__payment](../target/silver/tables/public__payment.md) | silver | 8 | ✅ | ✅ | — | 0/7 |
| [public__rental](../target/silver/tables/public__rental.md) | silver | 11 | ✅ | ✅ | ✅ | 0/8 |
| [public__staff](../target/silver/tables/public__staff.md) | silver | 11 | ✅ | ✅ | ✅ | 0/11 |
| [public__store](../target/silver/tables/public__store.md) | silver | 6 | ✅ | ✅ | ✅ | 0/4 |
