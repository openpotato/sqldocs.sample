# Table **film\_category**

This table is used to support a many\-to\-many relationship between films and categories\. For each category applied to a film, there will be one row in the [film\_category](../../tables/film_category) table listing the category and film\. The table refers to the [film](../../tables/film) and [category](../../tables/category) tables using foreign keys\.

## Schema

This table belongs to schema [sakila](../../schema).

## Columns

This table contains 3 columns.

**`film_id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    A foreign key identifying the film\.

**`category_id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    A foreign key identifying the category\.

**`last_update`**

:   [`timestamp(0) without time zone`](https://www.postgresql.org/docs/current/datatype-datetime.html) · `NOT NULL` · `CURRENT_TIMESTAMP`

    When the row was created or most recently updated\.

## Primary key

This table has a primary key.

**`film_category`**

:   `film_id, category_id`

## Foreign keys

This table has one foreign key.

**`fk_film_category_category`**

:   `category_id` » [`sakila.category (category_id)`](../../sakila/tables/category) · `ON UPDATE CASCADE` · `ON DELETE RESTRICT`

**`fk_film_category_film`**

:   `film_id` » [`sakila.film (film_id)`](../../sakila/tables/film) · `ON UPDATE CASCADE` · `ON DELETE RESTRICT`

## Indices

This table has one index.

**`film_category_pkey`**

:   `film_id, category_id`
