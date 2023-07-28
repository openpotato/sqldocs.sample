# Table **film**

This table is a list of all films potentially in stock in the stores\. The actual in\-stock copies of each film are represented in the inventory table\. The table refers to the [language](../../tables/language) table and is referred to by the [film\_category](../../tables/film_category), [film\_actor](../../tables/film_actor), and [inventory](../../tables/inventory) tables\.

## Schema

This table belongs to schema [sakila](../../schema).

## Columns

This table contains 13 columns.

**`film_id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    A surrogate primary key used to uniquely identify each film in the table\.

**`title`**

:   [`character varying(128)`](https://www.postgresql.org/docs/current/datatype-character.html) · `NOT NULL`

    The title of the film\.

**`description`**

:   [`text`](https://www.postgresql.org/docs/current/datatype-character.html)

    A short description or plot summary of the film\.

**`release_year`**

:   `sakila.yearonly` · `NULL::integer`

    The year in which the movie was released\.

**`language_id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    A foreign key pointing at the [language](../../tables/language) table; identifies the language of the film\.

**`original_language_id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html)

    A foreign key pointing at the [language](../../tables/language) table; identifies the original language of the film\. Used when a film has been dubbed into a new language\.

**`rental_duration`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL` · `3`

    The length of the rental period, in days\.

**`rental_rate`**

:   [`numeric(4,2)`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL` · `4.99`

    The cost to rent the film for the period specified in the `rental_duration` column\.

**`length`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html)

    The duration of the film, in minutes\.

**`replacement_cost`**

:   [`numeric(5,2)`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL` · `19.99`

    The amount charged to the customer if the film is not returned or is returned in a damaged state\.

**`rating`**

:   `sakila.rating` · `'G'::sakila.rating`

    The rating assigned to the film\. Can be one of: `G`, `PG`, `PG-13`, `R`, or `NC-17`\.

    Value | Description
    - | -
    G | General audiences – All ages admitted\.
    PG | Parental guidance suggested – Some material may not be suitable for children\.
    PG\-13 | Parents strongly cautioned – Some material may be inappropriate for children under 13\.
    R | Restricted – Under 17 requires accompanying parent or adult guardian\.
    NC\-17 | No children under 17 admitted\.

**`special_features`**

:   [`text[]`](https://www.postgresql.org/docs/current/datatype-character.html)

    Lists which common special features are included on the DVD\. Can be zero or more of: `Trailers`, `Commentaries`, `Deleted Scenes`, `Behind the Scenes`\.

**`last_update`**

:   [`timestamp(0) without time zone`](https://www.postgresql.org/docs/current/datatype-datetime.html) · `NOT NULL` · `CURRENT_TIMESTAMP`

    When the row was created or most recently updated\.

## Primary key

This table has a primary key.

**`film`**

:   `film_id`

## Foreign keys

This table has one foreign key.

**`fk_film_language`**

:   `language_id` » [`sakila.language (language_id)`](../../sakila/tables/language) · `ON UPDATE CASCADE` · `ON DELETE RESTRICT`

**`fk_film_language_original`**

:   `original_language_id` » [`sakila.language (language_id)`](../../sakila/tables/language) · `ON UPDATE CASCADE` · `ON DELETE RESTRICT`

## Indices

This table has 4 indices.

**`film_pkey`**

:   `film_id`

**`idx_film_fk_language_id`**

:   `language_id`

**`idx_film_fk_original_language_id`**

:   `original_language_id`

**`idx_film_title`**

:   `title`
