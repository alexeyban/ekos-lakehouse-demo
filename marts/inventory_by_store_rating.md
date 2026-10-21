---
mart: inventory_by_store_rating
grain: [store, rating]
dimensions:
  store: inventory.store_id
  rating: film.rating
measures:
  copies: count of inventory.inventory_id
  titles: count distinct inventory.film_id
---
Copies in stock and distinct film titles per store and film rating.
