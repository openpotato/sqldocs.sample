# Table **inventory**

This table contains one row for each copy of a given film in a given store\. The table refers to the [film](../../tables/film) and [store](../../tables/store) tables using foreign keys and is referred to by the [rental](../../tables/rental) table\.

## Schema

This table belongs to schema [sakila](../../schema).

## Columns

This table contains 4 columns.

**`inventory_id`**

:   [`integer`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    A surrogate primary key used to uniquely identify each item in inventory\.

**`film_id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    A foreign key pointing to the film this item represents\.

**`store_id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    A foreign key pointing to the store stocking this item\.

**`last_update`**

:   [`timestamp(0) without time zone`](https://www.postgresql.org/docs/current/datatype-datetime.html) · `NOT NULL` · `CURRENT_TIMESTAMP`

    When the row was created or most recently updated\.

## Primary key

This table has a primary key.

**`inventory`**

:   `inventory_id`

## Foreign keys

This table has one foreign key.

**`fk_inventory_film`**

:   `film_id` » [`sakila.film (film_id)`](../../sakila/tables/film) · `ON UPDATE CASCADE` · `ON DELETE RESTRICT`

**`fk_inventory_store`**

:   `store_id` » [`sakila.store (store_id)`](../../sakila/tables/store) · `ON UPDATE CASCADE` · `ON DELETE RESTRICT`

## Indices

This table has 3 indices.

**`inventory_pkey`**

:   `inventory_id`

**`idx_inventory_fk_film_id`**

:   `film_id`

**`idx_inventory_store_id_film_id`**

:   `film_id, store_id`
