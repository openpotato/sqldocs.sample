# Table **COUNTRY**

This table contains a list of countries\. The table is referred to by a foreign key in the [CITY](../../tables/city) table\.

## Columns

This table contains 3 columns.

**`COUNTRY_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    A surrogate primary key used to uniquely identify each country in the table\.

**`COUNTRY`**

:   [`VARCHAR(50)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes) · `NOT NULL`

    The name of the country\.

**`LAST_UPDATE`**

:   [`TIMESTAMP`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-datetime) · `NOT NULL` · `DEFAULT CURRENT_TIMESTAMP`

    When the row was created or most recently updated\.

## Primary key

This table has a primary key.

**`COUNTRY`**

:   `COUNTRY_ID`

## Indices

This table has one index.

**`RDB$PRIMARY5`**

:   `COUNTRY_ID`
