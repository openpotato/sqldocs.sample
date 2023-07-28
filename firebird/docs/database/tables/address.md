# Table **ADDRESS**

This table contains address information for customers, staff, and stores\. The table primary key appears as a foreign key in the [CUSTOMER](../../tables/customer), [STAFF](../../tables/staff), and [STORE](../../tables/store) tables\.

## Columns

This table contains 8 columns.

**`ADDRESS_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    A surrogate primary key used to uniquely identify each address in the table\.

**`ADDRESS`**

:   [`VARCHAR(50)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes) · `NOT NULL`

    The first line of an address\.

**`ADDRESS2`**

:   [`VARCHAR(50)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes) · `DEFAULT NULL`

    An optional second line of an address\.

**`DISTRICT`**

:   [`VARCHAR(20)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes) · `NOT NULL`

    The region of an address, this may be a state, province, prefecture, etc\.

**`CITY_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    A foreign key pointing to the [CITY](../../tables/city) table\.

**`POSTAL_CODE`**

:   [`VARCHAR(10)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes) · `DEFAULT NULL`

    The postal code or ZIP code of the address \(where applicable\)\.

**`PHONE`**

:   [`VARCHAR(20)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes) · `NOT NULL`

    The telephone number for the address\.

**`LAST_UPDATE`**

:   [`TIMESTAMP`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-datetime) · `NOT NULL` · `DEFAULT CURRENT_TIMESTAMP`

    When the row was created or most recently updated\.

## Primary key

This table has a primary key.

**`ADDRESS`**

:   `ADDRESS_ID`

## Foreign keys

This table has one foreign key.

**`FK_ADDRESS_CITY`**

:   `CITY_ID` » [`CITY (CITY_ID)`](../../tables/city) · `ON UPDATE CASCADE` · `ON DELETE NO ACTION`

## Indices

This table has 3 indices.

**`FK_ADDRESS_CITY`**

:   `CITY_ID`

**`IDX_ADDRESS_FK_CITY_ID`**

:   `CITY_ID`

**`RDB$PRIMARY2`**

:   `ADDRESS_ID`
