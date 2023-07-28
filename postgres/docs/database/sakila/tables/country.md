# Table **country**

This table contains a list of countries\. The table is referred to by a foreign key in the [CITY](../../tables/city) table\.

## Schema

This table belongs to schema [sakila](../../schema).

## Columns

This table contains 3 columns.

**`country_id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    A surrogate primary key used to uniquely identify each country in the table\.

**`country`**

:   [`character varying(50)`](https://www.postgresql.org/docs/current/datatype-character.html) · `NOT NULL`

    The name of the country\.

**`last_update`**

:   [`timestamp(0) without time zone`](https://www.postgresql.org/docs/current/datatype-datetime.html) · `NOT NULL` · `CURRENT_TIMESTAMP`

    When the row was created or most recently updated\.

## Primary key

This table has a primary key.

**`country`**

:   `country_id`

## Indices

This table has one index.

**`country_pkey`**

:   `country_id`
