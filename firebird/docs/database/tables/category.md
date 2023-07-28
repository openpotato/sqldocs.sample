# Table **CATEGORY**

This table lists the categories that can be assigned to a film\. The table is joined to the [FILM](../../tables/film) table by means of the [FILM\_CATEGORY](../../tables/film_category) table\.

## Columns

This table contains 3 columns.

**`CATEGORY_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    A surrogate primary key used to uniquely identify each category in the table\.

**`NAME`**

:   [`VARCHAR(25)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes) · `NOT NULL`

    The name of the category\.

**`LAST_UPDATE`**

:   [`TIMESTAMP`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-datetime) · `NOT NULL` · `DEFAULT CURRENT_TIMESTAMP`

    When the row was created or most recently updated\.

## Primary key

This table has a primary key.

**`CATEGORY`**

:   `CATEGORY_ID`

## Indices

This table has one index.

**`RDB$PRIMARY3`**

:   `CATEGORY_ID`
