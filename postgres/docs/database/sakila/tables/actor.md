# Table **actor**

This table lists information for all actors\. The table is joined to the [film](../../tables/film) table by means of the [film\_actor](../../tables/film_actor) table\.

## Schema

This table belongs to schema [sakila](../../schema).

## Columns

This table contains 4 columns.

**`actor_id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    A surrogate primary key used to uniquely identify each actor in the table\.

**`first_name`**

:   [`character varying(45)`](https://www.postgresql.org/docs/current/datatype-character.html) · `NOT NULL`

    The actor first name\.

**`last_name`**

:   [`character varying(45)`](https://www.postgresql.org/docs/current/datatype-character.html) · `NOT NULL`

    The actor last name\.

**`last_update`**

:   [`timestamp(0) without time zone`](https://www.postgresql.org/docs/current/datatype-datetime.html) · `NOT NULL` · `CURRENT_TIMESTAMP`

    When the row was created or most recently updated\.

## Primary key

This table has a primary key.

**`actor`**

:   `actor_id`

## Indices

This table has 2 indices.

**`actor_pkey`**

:   `actor_id`

**`idx_actor_last_name`**

:   `last_name`
