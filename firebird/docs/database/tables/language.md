# Table **LANGUAGE**

This table is a lookup table listing the possible languages that films can have for their language and original language values\. The table is referred to by the [FILM](../../tables/film) table\.

## Columns

This table contains 3 columns.

**`LANGUAGE_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    A surrogate primary key used to uniquely identify each language\.

**`NAME`**

:   [`CHAR(20)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes) · `NOT NULL`

    The English name of the language\.

**`LAST_UPDATE`**

:   [`TIMESTAMP`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-datetime) · `NOT NULL` · `DEFAULT CURRENT_TIMESTAMP`

    When the row was created or most recently updated\.

## Primary key

This table has a primary key.

**`LANGUAGE`**

:   `LANGUAGE_ID`

## Indices

This table has one index.

**`RDB$PRIMARY12`**

:   `LANGUAGE_ID`
