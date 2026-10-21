---
title: "public.payment"
order: 112
ekos_generated: true
---

# public.payment

<!-- ekos:manual id="source-public.payment" -->
_Business meaning of this table, known quirks, data owner._
<!-- /ekos:manual -->

## Columns

| # | Column | Type | Null | Default | Key | References | Allowed values | PII candidate | Comment |
|---|---|---|---|---|---|---|---|---|---|
| 1 | `payment_id` | `integer` | NOT NULL | yes | PK |  |  |  |  |
| 2 | `customer_id` | `integer` | NOT NULL |  |  |  |  |  |  |
| 3 | `staff_id` | `integer` | NOT NULL |  |  |  |  |  |  |
| 4 | `rental_id` | `integer` | NOT NULL |  |  |  |  |  |  |
| 5 | `amount` | `numeric(5,2)` | NOT NULL |  |  |  |  |  |  |
| 6 | `payment_date` | `timestamp with time zone` | NOT NULL |  | PK |  |  |  |  |
| 7 | `uuid` | `uuid` | NOT NULL | yes |  |  |  |  |  |

## Relations

_None._

## Load into bronze

|  |  |
|---|---|
| Bronze table | `bronze_public.payment` |
| Mode | full |
| Hard deletes | replaced with the table |
| Evidence | about 51061 rows |
| Notes | payment_date is declared, but no BEFORE UPDATE row trigger assigns NEW.payment_date: an update that does not touch it would be missed, so the table is loaded in full |

Last reconciliation: **✅ green** — control fired. [Details](../../quality/reconciliation.md)

## Downstream

Silver model: [public__payment](../../target/silver/tables/public__payment.md)

| Column | Silver | Gold | Other models |
|---|---|---|---|
| `payment_id` | `public__payment.payment_id` |  |  |
| `customer_id` | `public__payment.customer_id` |  |  |
| `staff_id` | `public__payment.staff_id` |  |  |
| `rental_id` | `public__payment.rental_id` |  |  |
| `amount` | `public__payment.amount` |  |  |
| `payment_date` | `public__payment.payment_date` |  |  |
| `uuid` | `public__payment.uuid` |  |  |
