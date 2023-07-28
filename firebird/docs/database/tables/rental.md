# Table **RENTAL**

This table contains one row for each rental of each inventory item with information about who rented what item, when it was rented, and when it was returned\. The table refers to the [INVENTORY](../../tables/inventory), [CUSTOMER](../../tables/customer), and [STAFF](../../tables/staff) tables and is referred to by the [PAYMENT](../../tables/payment) table\.

## Columns

This table contains 7 columns.

**`RENTAL_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    A surrogate primary key that uniquely identifies the rental\.

**`RENTAL_DATE`**

:   [`TIMESTAMP`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-datetime) · `NOT NULL`

    The date and time that the item was rented\.

**`INVENTORY_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    The item being rented\.

**`CUSTOMER_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    The customer renting the item\.

**`RETURN_DATE`**

:   [`TIMESTAMP`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-datetime) · `DEFAULT NULL`

    The date and time the item was returned\.

**`STAFF_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    The staff member who processed the rental\.

**`LAST_UPDATE`**

:   [`TIMESTAMP`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-datetime) · `NOT NULL` · `DEFAULT CURRENT_TIMESTAMP`

    When the row was created or most recently updated\.

## Primary key

This table has a primary key.

**`RENTAL`**

:   `RENTAL_ID`

## Foreign keys

This table has one foreign key.

**`FK_RENTAL_CUSTOMER`**

:   `CUSTOMER_ID` » [`CUSTOMER (CUSTOMER_ID)`](../../tables/customer) · `ON UPDATE CASCADE` · `ON DELETE NO ACTION`

**`FK_RENTAL_INVENTORY`**

:   `INVENTORY_ID` » [`INVENTORY (INVENTORY_ID)`](../../tables/inventory) · `ON UPDATE CASCADE` · `ON DELETE NO ACTION`

**`FK_RENTAL_STAFF`**

:   `STAFF_ID` » [`STAFF (STAFF_ID)`](../../tables/staff) · `ON UPDATE CASCADE` · `ON DELETE NO ACTION`

## Indices

This table has 8 indices.

**`FK_RENTAL_CUSTOMER`**

:   `CUSTOMER_ID`

**`FK_RENTAL_INVENTORY`**

:   `INVENTORY_ID`

**`FK_RENTAL_STAFF`**

:   `STAFF_ID`

**`IDX_RENTAL`**

:   `RENTAL_DATE, INVENTORY_ID, CUSTOMER_ID`

**`IDX_RENTAL_FK_CUSTOMER_ID`**

:   `CUSTOMER_ID`

**`IDX_RENTAL_FK_INVENTORY_ID`**

:   `INVENTORY_ID`

**`IDX_RENTAL_FK_STAFF_ID`**

:   `STAFF_ID`

**`RDB$PRIMARY14`**

:   `RENTAL_ID`
