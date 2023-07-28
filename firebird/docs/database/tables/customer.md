# Table **CUSTOMER**

This table contains a list of all customers\. The table is referred to in the [PAYMENT](../../tables/payment) and [RENTAL](../../tables/rental) tables and refers to the [ADDRESS](../../tables/address) and [STORE](../../tables/store) tables using foreign keys\.

## Columns

This table contains 9 columns.

**`CUSTOMER_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    A surrogate primary key used to uniquely identify each customer in the table\.

**`STORE_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    A foreign key identifying the customer *home store*\. Customers are not limited to renting only from this store, but this is the store at which they generally shop\.

**`FIRST_NAME`**

:   [`VARCHAR(45)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes) · `NOT NULL`

    The customer first name\.

**`LAST_NAME`**

:   [`VARCHAR(45)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes) · `NOT NULL`

    The customer last name\.

**`EMAIL`**

:   [`VARCHAR(50)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes) · `DEFAULT NULL`

    The customer email address\.

**`ADDRESS_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    A foreign key identifying the customer address in the [ADDRESS](../../tables/address) table\.

**`ACTIVE`**

:   [`BOOLEAN`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-booleantypes) · `NOT NULL` · `DEFAULT TRUE`

    Indicates whether the customer is an active customer\. Setting this to `FALSE` serves as an alternative to deleting a customer outright\. Most queries should have a `WHERE ACTIVE = TRUE` clause\.

**`CREATE_DATE`**

:   [`TIMESTAMP`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-datetime) · `NOT NULL` · `DEFAULT CURRENT_TIMESTAMP`

    The date the customer was added to the system\. This date is automatically set using a trigger during an INSERT\.

**`LAST_UPDATE`**

:   [`TIMESTAMP`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-datetime) · `NOT NULL` · `DEFAULT CURRENT_TIMESTAMP`

    When the row was created or most recently updated\.

## Primary key

This table has a primary key.

**`CUSTOMER`**

:   `CUSTOMER_ID`

## Foreign keys

This table has one foreign key.

**`FK_CUSTOMER_ADDRESS`**

:   `ADDRESS_ID` » [`ADDRESS (ADDRESS_ID)`](../../tables/address) · `ON UPDATE CASCADE` · `ON DELETE NO ACTION`

**`FK_CUSTOMER_STORE`**

:   `STORE_ID` » [`STORE (STORE_ID)`](../../tables/store) · `ON UPDATE CASCADE` · `ON DELETE NO ACTION`

## Indices

This table has 6 indices.

**`FK_CUSTOMER_ADDRESS`**

:   `ADDRESS_ID`

**`FK_CUSTOMER_STORE`**

:   `STORE_ID`

**`IDX_CUSTOMER_FK_ADDRESS_ID`**

:   `ADDRESS_ID`

**`IDX_CUSTOMER_FK_STORE_ID`**

:   `STORE_ID`

**`IDX_CUSTOMER_LAST_NAME`**

:   `LAST_NAME`

**`RDB$PRIMARY6`**

:   `CUSTOMER_ID`
