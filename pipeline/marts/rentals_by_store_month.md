---
mart: rentals_by_store_month
grain: [store, month]
dimensions:
  store: inventory.store_id
  month: month of rental.rented_at
measures:
  rentals: count of rental.rental_id
---
Rental count per store per month.
