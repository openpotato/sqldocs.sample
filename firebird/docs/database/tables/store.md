# Table **STORE**

This table lists all stores in the system\. All inventory is assigned to specific stores, and staff and customers are assigned a *home store*\. The table refers to the [STAFF](../../tables/staff) and [ADDRESS](../../tables/address) tables using foreign keys and is referred to by the [STAFF](../../tables/staff), [CUSTOMER](../../tables/customer), and [INVENTORY](../../tables/inventory) tables\.

## Columns

This table contains 4 columns.

**`STORE_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    A surrogate primary key that uniquely identifies the store\.

**`MANAGER_STAFF_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    A foreign key identifying the manager of this store\.

**`ADDRESS_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    A foreign key identifying the address of this store\.

**`LAST_UPDATE`**

:   [`TIMESTAMP`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-datetime) · `NOT NULL` · `DEFAULT CURRENT_TIMESTAMP`

    When the row was created or most recently updated\.

## Primary key

This table has a primary key.

**`STORE`**

:   `STORE_ID`

## Foreign keys

This table has one foreign key.

**`FK_STORE_ADDRESS`**

:   `ADDRESS_ID` » [`ADDRESS (ADDRESS_ID)`](../../tables/address) · `ON UPDATE CASCADE` · `ON DELETE NO ACTION`

**`FK_STORE_STAFF`**

:   `MANAGER_STAFF_ID` » [`STAFF (STAFF_ID)`](../../tables/staff) · `ON UPDATE CASCADE` · `ON DELETE NO ACTION`

## Indices

This table has 5 indices.

**`FK_STORE_ADDRESS`**

:   `ADDRESS_ID`

**`FK_STORE_STAFF`**

:   `MANAGER_STAFF_ID`

**`IDX_STORE_FK_ADDRESS`**

:   `ADDRESS_ID`

**`IDX_STORE_FK_MANAGER_STAFF_ID`**

:   `MANAGER_STAFF_ID`

**`RDB$PRIMARY16`**

:   `STORE_ID`
