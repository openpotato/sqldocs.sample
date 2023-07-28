# Table **address**

This table contains address information for customers, staff, and stores\. The table primary key appears as a foreign key in the [customer](../../tables/customer), [staff](../../tables/staff), and [store](../../tables/store) tables\.

## Schema

This table belongs to schema [sakila](../../schema).

## Columns

This table contains 8 columns.

**`address_id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    A surrogate primary key used to uniquely identify each address in the table\.

**`address`**

:   [`character varying(50)`](https://www.postgresql.org/docs/current/datatype-character.html) · `NOT NULL`

    The first line of an address\.

**`address2`**

:   [`character varying(50)`](https://www.postgresql.org/docs/current/datatype-character.html) · `NULL::character varying`

    An optional second line of an address\.

**`district`**

:   [`character varying(20)`](https://www.postgresql.org/docs/current/datatype-character.html) · `NOT NULL`

    The region of an address, this may be a state, province, prefecture, etc\.

**`city_id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    A foreign key pointing to the [city](../../tables/city) table\.

**`postal_code`**

:   [`character varying(10)`](https://www.postgresql.org/docs/current/datatype-character.html) · `NULL::character varying`

    The postal code or ZIP code of the address \(where applicable\)\.

**`phone`**

:   [`character varying(20)`](https://www.postgresql.org/docs/current/datatype-character.html) · `NOT NULL`

    The telephone number for the address\.

**`last_update`**

:   [`timestamp(0) without time zone`](https://www.postgresql.org/docs/current/datatype-datetime.html) · `NOT NULL` · `CURRENT_TIMESTAMP`

    When the row was created or most recently updated\.

## Primary key

This table has a primary key.

**`address`**

:   `address_id`

## Foreign keys

This table has one foreign key.

**`fk_address_city`**

:   `city_id` » [`sakila.city (city_id)`](../../sakila/tables/city) · `ON UPDATE CASCADE` · `ON DELETE RESTRICT`

## Indices

This table has 2 indices.

**`address_pkey`**

:   `address_id`

**`idx_address_fk_city_id`**

:   `city_id`
