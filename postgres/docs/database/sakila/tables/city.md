# Table **city**

This table contains a list of cities\. The table is referred to by a foreign key in the [address](../../tables/address) table and refers to the [country](../../tables/country) table using a foreign key\.

## Schema

This table belongs to schema [sakila](../../schema).

## Columns

This table contains 4 columns.

**`city_id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    A surrogate primary key used to uniquely identify each city in the table\.

**`city`**

:   [`character varying(50)`](https://www.postgresql.org/docs/current/datatype-character.html) · `NOT NULL`

    The name of the city\.

**`country_id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    A foreign key identifying the country that the city belongs to\.

**`last_update`**

:   [`timestamp(0) without time zone`](https://www.postgresql.org/docs/current/datatype-datetime.html) · `NOT NULL` · `CURRENT_TIMESTAMP`

    When the row was created or most recently updated\.

## Primary key

This table has a primary key.

**`city`**

:   `city_id`

## Foreign keys

This table has one foreign key.

**`fk_city_country`**

:   `country_id` » [`sakila.country (country_id)`](../../sakila/tables/country) · `ON UPDATE CASCADE` · `ON DELETE RESTRICT`

## Indices

This table has 2 indices.

**`city_pkey`**

:   `city_id`

**`idx_city_fk_country_id`**

:   `country_id`
