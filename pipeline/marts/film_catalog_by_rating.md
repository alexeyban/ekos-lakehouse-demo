---
mart: film_catalog_by_rating
grain: [rating]
dimensions:
  rating: film.rating
measures:
  films: count of film.film_id
  average_rental_rate: average of film.rental_rate
  average_length: average of film.length
  total_replacement_cost: sum of film.replacement_cost
---
The film catalogue per rating: how many films, their average rental rate and length, and what replacing every film would cost.
