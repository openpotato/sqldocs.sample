# Table **category**

This table lists the categories that can be assigned to a film\. The table is joined to the [film](../../tables/film) table by means of the [film\_category](../../tables/film_category) table\.

## Schema

This table belongs to schema [sakila](../../schema).

## Columns

This table contains 3 columns.

**`category_id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    A surrogate primary key used to uniquely identify each category in the table\.

**`name`**

:   [`character varying(25)`](https://www.postgresql.org/docs/current/datatype-character.html) · `NOT NULL`

    The name of the category\.

**`last_update`**

:   [`timestamp(0) without time zone`](https://www.postgresql.org/docs/current/datatype-datetime.html) · `NOT NULL` · `CURRENT_TIMESTAMP`

    When the row was created or most recently updated\.

## Primary key

This table has a primary key.

**`category`**

:   `category_id`

## Indices

This table has one index.

**`category_pkey`**

:   `category_id`
