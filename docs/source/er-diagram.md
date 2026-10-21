---
title: "Source ER diagram"
order: 31
ekos_generated: true
---

# Source ER diagram

Entities are source tables; relationships are declared foreign keys (child `}o--||` parent; `o|` when the FK column is nullable). Each table page shows its neighbourhood with every column.

## Schema `public`

```mermaid
erDiagram
  public_actor {
    integer actor_id PK
    text first_name
    text last_name
    timestamp_with_time_zone last_update
  }
  public_address {
    integer address_id PK
    text address
    text address2
    text district
    integer city_id FK
    text postal_code
    text phone
    timestamp_with_time_zone last_update
  }
  public_category {
    integer category_id PK
    text name
    timestamp_with_time_zone last_update
  }
  public_city {
    integer city_id PK
    text city
    integer country_id FK
    timestamp_with_time_zone last_update
  }
  public_country {
    integer country_id PK
    text country
    timestamp_with_time_zone last_update
  }
  public_customer {
    integer customer_id PK
    integer store_id FK
    text first_name
    text last_name
    text email
    integer address_id FK
    boolean activebool
    date create_date
    timestamp_with_time_zone last_update
    integer active
    uuid uuid
    text loyalty_tier
  }
  public_film {
    integer film_id PK
    text title
    text description
    year release_year
    integer language_id FK
    integer original_language_id FK
    smallint rental_duration
    numeric rental_rate
    smallint length
    numeric replacement_cost
    mpaa_rating rating
    timestamp_with_time_zone last_update
    text special_features
    tsvector fulltext
    numeric length_hours
  }
  public_film_actor {
    integer actor_id PK,FK
    integer film_id PK,FK
    timestamp_with_time_zone last_update
  }
  public_film_category {
    integer film_id PK,FK
    integer category_id PK,FK
    timestamp_with_time_zone last_update
  }
  public_film_embedding {
    integer film_id PK,FK
    vector embedding
    timestamp_with_time_zone last_update
  }
  public_inventory {
    integer inventory_id PK
    integer film_id FK
    integer store_id FK
    timestamp_with_time_zone last_update
  }
  public_language {
    integer language_id PK
    text name
    timestamp_with_time_zone last_update
  }
  public_payment {
    integer payment_id PK
    integer customer_id
    integer staff_id
    integer rental_id
    numeric amount
    timestamp_with_time_zone payment_date PK
    uuid uuid
  }
  public_rental {
    integer rental_id PK
    timestamp_with_time_zone rented_at
    integer inventory_id FK
    integer customer_id FK
    timestamp_with_time_zone return_date
    integer staff_id FK
    timestamp_with_time_zone last_update
    uuid uuid
  }
  public_staff {
    integer staff_id PK
    text first_name
    text last_name
    integer address_id FK
    text email
    integer store_id FK
    boolean active
    text username
    text password
    timestamp_with_time_zone last_update
    bytea picture
  }
  public_store {
    integer store_id PK
    integer manager_staff_id
    integer address_id FK
    timestamp_with_time_zone last_update
  }
  public_address }o--|| public_city : "city_id"
  public_city }o--|| public_country : "country_id"
  public_customer }o--|| public_address : "address_id"
  public_customer }o--|| public_store : "store_id"
  public_film }o--|| public_language : "language_id"
  public_film }o--o| public_language : "original_language_id"
  public_film_actor }o--|| public_actor : "actor_id"
  public_film_actor }o--|| public_film : "film_id"
  public_film_category }o--|| public_category : "category_id"
  public_film_category }o--|| public_film : "film_id"
  public_film_embedding }o--|| public_film : "film_id"
  public_inventory }o--|| public_film : "film_id"
  public_inventory }o--|| public_store : "store_id"
  public_rental }o--|| public_customer : "customer_id"
  public_rental }o--|| public_inventory : "inventory_id"
  public_rental }o--|| public_staff : "staff_id"
  public_staff }o--|| public_address : "address_id"
  public_staff }o--|| public_store : "store_id"
  public_store }o--|| public_address : "address_id"
```
