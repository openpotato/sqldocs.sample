# Table **FILM\_TEXT**

This table contains the `FILM_ID`, `TITLE` and `DESCRIPTION` columns of the [FILM](../../tables/film) table, with the contents of the table kept in synchrony with the [FILM](../../tables/film) table by means of triggers on [film](../../tables/film) table `INSERT`, `UPDATE` and `DELETE` operations\.

## Columns

This table contains 3 columns.

**`FILM_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    A surrogate primary key used to uniquely identify each film in the table\.

**`TITLE`**

:   [`VARCHAR(255)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes) · `NOT NULL`

    The title of the film\.

**`DESCRIPTION`**

:   [`BLOB subtype text`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-bnrytypes)

    A short description or plot summary of the film\.

## Primary key

This table has a primary key.

**`FILM_TEXT`**

:   `FILM_ID`

## Indices

This table has one index.

**`RDB$PRIMARY10`**

:   `FILM_ID`
