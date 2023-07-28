# Table **film\_text**

This table contains the `film_id`, `title` and `description` columns of the [film](../../tables/film) table, with the contents of the table kept in synchrony with the [film](../../tables/film) table by means of triggers on [film](../../tables/film) table `INSERT`, `UPDATE` and `DELETE` operations\.

## Schema

This table belongs to schema [sakila](../../schema).

## Columns

This table contains 3 columns.

**`film_id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    A surrogate primary key used to uniquely identify each film in the table\.

**`title`**

:   [`character varying(255)`](https://www.postgresql.org/docs/current/datatype-character.html) · `NOT NULL`

    The title of the film\.

**`description`**

:   [`text`](https://www.postgresql.org/docs/current/datatype-character.html)

    A short description or plot summary of the film\.

## Primary key

This table has a primary key.

**`film_text`**

:   `film_id`

## Indices

This table has 2 indices.

**`film_text_pkey`**

:   `film_id`

**`idx_film_text_title_description`**

:   `title, description`
