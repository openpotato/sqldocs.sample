# Table **film\_actor**

This table is used to support a many\-to\-many relationship between films and actors\. For each actor in a given film, there will be one row in the [film\_actor](../../tables/film_actor) table listing the actor and film\. The table refers to the [film](../../tables/film) and [actor](../../tables/actor) tables using foreign keys\.

## Schema

This table belongs to schema [sakila](../../schema).

## Columns

This table contains 3 columns.

**`actor_id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    A foreign key identifying the actor\.

**`film_id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    A foreign key identifying the film\.

**`last_update`**

:   [`timestamp(0) without time zone`](https://www.postgresql.org/docs/current/datatype-datetime.html) · `NOT NULL` · `CURRENT_TIMESTAMP`

    When the row was created or most recently updated\.

## Primary key

This table has a primary key.

**`film_actor`**

:   `actor_id, film_id`

## Foreign keys

This table has one foreign key.

**`fk_film_actor_actor`**

:   `actor_id` » [`sakila.actor (actor_id)`](../../sakila/tables/actor) · `ON UPDATE CASCADE` · `ON DELETE RESTRICT`

**`fk_film_actor_film`**

:   `film_id` » [`sakila.film (film_id)`](../../sakila/tables/film) · `ON UPDATE CASCADE` · `ON DELETE RESTRICT`

## Indices

This table has 2 indices.

**`film_actor_pkey`**

:   `actor_id, film_id`

**`idx_film_actor_fk_film_id`**

:   `film_id`
