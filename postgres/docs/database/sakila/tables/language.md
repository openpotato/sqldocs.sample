# Table **language**

This table is a lookup table listing the possible languages that films can have for their language and original language values\. The table is referred to by the [film](../../tables/film) table\.

## Schema

This table belongs to schema [sakila](../../schema).

## Columns

This table contains 3 columns.

**`language_id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    A surrogate primary key used to uniquely identify each language\.

**`name`**

:   [`character(20)`](https://www.postgresql.org/docs/current/datatype-character.html) · `NOT NULL`

    The English name of the language\.

**`last_update`**

:   [`timestamp(0) without time zone`](https://www.postgresql.org/docs/current/datatype-datetime.html) · `NOT NULL` · `CURRENT_TIMESTAMP`

    When the row was created or most recently updated\.

## Primary key

This table has a primary key.

**`language`**

:   `language_id`

## Indices

This table has one index.

**`language_pkey`**

:   `language_id`
