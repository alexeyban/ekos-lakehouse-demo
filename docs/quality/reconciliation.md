---
title: "Reconciliation results"
order: 61
ekos_generated: true
---

# Reconciliation results

> Evidence collected 2026-10-21 15:32 UTC at pipeline commit `efeeffd`.

Each table is compared between the source and bronze on every run. A tier that agrees proves nothing unless the planted control — one deliberately altered row — is detected; a missed control marks the result **unverified**.

| Table | Verdict | Tiers | Control | Not compared | Control detail |
|---|---|---|---|---|---|
| [public.actor](../source/tables/public.actor.md) | ✅ green | V1: ✅<br>V2: ✅<br>V3: ✅ | fired |  | one row's last_update changed in the query |
| [public.address](../source/tables/public.address.md) | ✅ green | V1: ✅<br>V2: ✅<br>V3: ✅ | fired |  | one row's last_update changed in the query |
| [public.category](../source/tables/public.category.md) | ✅ green | V1: ✅<br>V2: ✅<br>V3: ✅ | fired |  | one row's last_update changed in the query |
| [public.city](../source/tables/public.city.md) | ✅ green | V1: ✅<br>V2: ✅<br>V3: ✅ | fired |  | one row's last_update changed in the query |
| [public.country](../source/tables/public.country.md) | ✅ green | V1: ✅<br>V2: ✅<br>V3: ✅ | fired |  | one row's last_update changed in the query |
| [public.customer](../source/tables/public.customer.md) | ✅ green | V1: ✅<br>V2: ✅<br>V3: ✅ | fired |  | one row's loyalty_tier changed in the query |
| [public.film](../source/tables/public.film.md) | ✅ green | V1: ✅<br>V2: ✅<br>V3: ✅ | fired | special_features (text[]) | one row's length_hours changed in the query |
| [public.film_actor](../source/tables/public.film_actor.md) | ✅ green | V1: ✅<br>V2: ✅<br>V3: ✅ | fired |  | one row's last_update changed in the query |
| [public.film_category](../source/tables/public.film_category.md) | ✅ green | V1: ✅<br>V2: ✅<br>V3: ✅ | fired |  | one row's last_update changed in the query |
| [public.film_embedding](../source/tables/public.film_embedding.md) | ✅ green | V1: ✅<br>V2: ✅<br>V3: ✅ | fired | embedding (vector(20)) | one row's last_update changed in the query |
| [public.inventory](../source/tables/public.inventory.md) | ✅ green | V1: ✅<br>V2: ✅<br>V3: ✅ | fired |  | one row's last_update changed in the query |
| [public.language](../source/tables/public.language.md) | ✅ green | V1: ✅<br>V2: ✅<br>V3: ✅ | fired |  | one row's last_update changed in the query |
| [public.payment](../source/tables/public.payment.md) | ✅ green | V1: ✅<br>V2: ✅<br>V3: ✅ | fired |  | one row's uuid changed in the query |
| [public.rental](../source/tables/public.rental.md) | ✅ green | V1: ✅<br>V2: ✅<br>V3: ✅ | fired |  | one row's uuid changed in the query |
| [public.staff](../source/tables/public.staff.md) | ✅ green | V1: ✅<br>V2: ✅<br>V3: ✅ | fired |  | one row's picture changed in the query |
| [public.store](../source/tables/public.store.md) | ✅ green | V1: ✅<br>V2: ✅<br>V3: ✅ | fired |  | one row's last_update changed in the query |
