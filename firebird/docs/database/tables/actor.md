# Table **ACTOR**

This table lists information for all actors\. The table is joined to the [FILM](../../tables/film) table by means of the [FILM\_ACTOR](../../tables/film_actor) table\.

## Columns

This table contains 4 columns.

**`ACTOR_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    A surrogate primary key used to uniquely identify each actor in the table\.

**`FIRST_NAME`**

:   [`VARCHAR(45)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes) · `NOT NULL`

    The actor first name\.

**`LAST_NAME`**

:   [`VARCHAR(45)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes) · `NOT NULL`

    The actor last name\.

**`LAST_UPDATE`**

:   [`TIMESTAMP`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-datetime) · `NOT NULL` · `DEFAULT CURRENT_TIMESTAMP`

    When the row was created or most recently updated\.

## Primary key

This table has a primary key.

**`ACTOR`**

:   `ACTOR_ID`

## Indices

This table has 2 indices.

**`ACTOR_IDX_LAST_NAME`**

:   `LAST_NAME`

**`RDB$PRIMARY1`**

:   `ACTOR_ID`
