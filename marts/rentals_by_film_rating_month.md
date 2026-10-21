---
mart: rentals_by_film_rating_month
grain: [rating, month]
dimensions:
  rating: film.rating
  month: month of rental.rented_at
measures:
  rentals: count of rental.rental_id
  customers: count distinct rental.customer_id
---
Rentals and distinct renting customers per film rating per month.
