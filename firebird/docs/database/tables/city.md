# Table **CITY**

This table contains a list of cities\. The table is referred to by a foreign key in the [ADDRESS](../../tables/address) table and refers to the [COUNTRY](../../tables/country) table using a foreign key\.

## Columns

This table contains 4 columns.

**`CITY_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    A surrogate primary key used to uniquely identify each city in the table\.

**`CITY`**

:   [`VARCHAR(50)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes) · `NOT NULL`

    The name of the city\.

**`COUNTRY_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    A foreign key identifying the country that the city belongs to\.

**`LAST_UPDATE`**

:   [`TIMESTAMP`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-datetime) · `NOT NULL` · `DEFAULT CURRENT_TIMESTAMP`

    When the row was created or most recently updated\.

## Primary key

This table has a primary key.

**`CITY`**

:   `CITY_ID`

## Foreign keys

This table has one foreign key.

**`FK_CITY_COUNTRY`**

:   `COUNTRY_ID` » [`COUNTRY (COUNTRY_ID)`](../../tables/country) · `ON UPDATE CASCADE` · `ON DELETE NO ACTION`

## Indices

This table has 3 indices.

**`FK_CITY_COUNTRY`**

:   `COUNTRY_ID`

**`IDX_CITY_FK_COUNTRY_ID`**

:   `COUNTRY_ID`

**`RDB$PRIMARY4`**

:   `CITY_ID`
