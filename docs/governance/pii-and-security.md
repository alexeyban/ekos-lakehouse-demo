---
title: "PII and security"
order: 72
ekos_generated: true
---

# PII and security

PII candidates come from EKOS's name classifier (RFC 0157) and are **reported, never applied**. A person approves masking per column in `[extensions.lakehouse.pii]`: `null` keeps the column without values, `hmac` replaces each value with HMAC-SHA256 under `EKOS_LH_PII_KEY` (from the environment; compiled SQL under `dbt/target/` is git-ignored).

> Bronze keeps source values unmasked. Restrict bronze namespaces to the pipeline's service identities.

| Column | Classifier | Silver masking | Reaches |
|---|---|---|---|
| `public.actor.first_name` | personname | ⚠️ not masked | `public__actor.first_name` |
| `public.actor.last_name` | personname | ⚠️ not masked | `public__actor.last_name` |
| `public.address.address_id` | postaladdress | ⚠️ not masked | `public__address.address_id` |
| `public.address.address` | postaladdress | ⚠️ not masked | `public__address.address` |
| `public.address.address2` | postaladdress | ⚠️ not masked | `public__address.address2` |
| `public.address.postal_code` | postaladdress | ⚠️ not masked | `public__address.postal_code` |
| `public.address.phone` | phone | ⚠️ not masked | `public__address.phone` |
| `public.customer.first_name` | personname | ⚠️ not masked | `public__customer.first_name` |
| `public.customer.last_name` | personname | ⚠️ not masked | `public__customer.last_name` |
| `public.customer.email` | email | ⚠️ not masked | `public__customer.email` |
| `public.customer.address_id` | postaladdress | ⚠️ not masked | `public__customer.address_id` |
| `public.staff.first_name` | personname | ⚠️ not masked | `public__staff.first_name` |
| `public.staff.last_name` | personname | ⚠️ not masked | `public__staff.last_name` |
| `public.staff.address_id` | postaladdress | ⚠️ not masked | `public__staff.address_id` |
| `public.staff.email` | email | ⚠️ not masked | `public__staff.email` |
| `public.staff.password` | credential | ⚠️ not masked | `public__staff.password` |
| `public.store.address_id` | postaladdress | ⚠️ not masked | `public__store.address_id` |

## Credentials

Configuration names environment variables, never secrets:

| Secret | Where it is read |
|---|---|
| Source password | `source-password-env` in `[extensions.lakehouse]` |
| Masking key | `EKOS_LH_PII_KEY` |
| Alert webhook | `alert-webhook-env` |

## Access

<!-- ekos:manual id="pii-access" -->
_Who can read bronze, silver and gold; how access is requested and reviewed; data retention per layer._
<!-- /ekos:manual -->
