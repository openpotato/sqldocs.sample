# Table **FILM\_CATEGORY**

This table is used to support a many\-to\-many relationship between films and categories\. For each category applied to a film, there will be one row in the [FILM\_CATEGORY](../../tables/film_category) table listing the category and film\. The table refers to the [FILM](../../tables/film) and [CATEGORY](../../tables/category) tables using foreign keys\.

## Columns

This table contains 3 columns.

**`FILM_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    A foreign key identifying the film\.

**`CATEGORY_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    A foreign key identifying the category\.

**`LAST_UPDATE`**

:   [`TIMESTAMP`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-datetime) · `NOT NULL` · `DEFAULT CURRENT_TIMESTAMP`

    When the row was created or most recently updated\.

## Primary key

This table has a primary key.

**`FILM_CATEGORY`**

:   `FILM_ID, CATEGORY_ID`

## Foreign keys

This table has one foreign key.

**`FK_FILM_CATEGORY_CATEGORY`**

:   `CATEGORY_ID` » [`CATEGORY (CATEGORY_ID)`](../../tables/category) · `ON UPDATE CASCADE` · `ON DELETE NO ACTION`

**`FK_FILM_CATEGORY_FILM`**

:   `FILM_ID` » [`FILM (FILM_ID)`](../../tables/film) · `ON UPDATE CASCADE` · `ON DELETE NO ACTION`

## Indices

This table has 5 indices.

**`FILM_CATEGORY_IDX_FK_CATEGORY`**

:   `CATEGORY_ID`

**`FILM_CATEGORY_IDX_FK_FILM`**

:   `FILM_ID`

**`FK_FILM_CATEGORY_CATEGORY`**

:   `CATEGORY_ID`

**`FK_FILM_CATEGORY_FILM`**

:   `FILM_ID`

**`RDB$PRIMARY9`**

:   `FILM_ID, CATEGORY_ID`
