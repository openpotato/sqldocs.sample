# Table **INVENTORY**

This table contains one row for each copy of a given film in a given store\. The table refers to the [FILM](../../tables/film) and [STORE](../../tables/store) tables using foreign keys and is referred to by the [RENTAL](../../tables/rental) table\.

## Columns

This table contains 4 columns.

**`INVENTORY_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    A surrogate primary key used to uniquely identify each item in inventory\.

**`FILM_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    A foreign key pointing to the film this item represents\.

**`STORE_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    A foreign key pointing to the store stocking this item\.

**`LAST_UPDATE`**

:   [`TIMESTAMP`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-datetime) · `NOT NULL` · `DEFAULT CURRENT_TIMESTAMP`

    When the row was created or most recently updated\.

## Primary key

This table has a primary key.

**`INVENTORY`**

:   `INVENTORY_ID`

## Foreign keys

This table has one foreign key.

**`FK_INVENTORY_FILM`**

:   `FILM_ID` » [`FILM (FILM_ID)`](../../tables/film) · `ON UPDATE CASCADE` · `ON DELETE NO ACTION`

**`FK_INVENTORY_STORE`**

:   `STORE_ID` » [`STORE (STORE_ID)`](../../tables/store) · `ON UPDATE CASCADE` · `ON DELETE NO ACTION`

## Indices

This table has 5 indices.

**`FK_INVENTORY_FILM`**

:   `FILM_ID`

**`FK_INVENTORY_STORE`**

:   `STORE_ID`

**`IDX_INVENTORY_FK_FILM_ID`**

:   `FILM_ID`

**`IDX_INVENTORY_FK_FILM_ID_STORE_ID`**

:   `STORE_ID, FILM_ID`

**`RDB$PRIMARY11`**

:   `INVENTORY_ID`
