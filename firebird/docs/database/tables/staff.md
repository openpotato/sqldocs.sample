# Table **STAFF**

This table lists all staff members, including information for email address, login information, and picture\. The table refers to the [STORE](../../tables/store) and [ADDRESS](../../tables/address) tables using foreign keys, and is referred to by the [RENTAL](../../tables/rental), [PAYMENT](../../tables/payment), and [STORE](../../tables/store) tables\.

## Columns

This table contains 11 columns.

**`STAFF_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    A surrogate primary key that uniquely identifies the staff member\.

**`FIRST_NAME`**

:   [`VARCHAR(45)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes) · `NOT NULL`

    The first name of the staff member\.

**`LAST_NAME`**

:   [`VARCHAR(45)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes) · `NOT NULL`

    The last name of the staff member\.

**`ADDRESS_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    A foreign key to the staff member address in the [ADDRESS](../../tables/address) table\.

**`PICTURE`**

:   [`BLOB subtype binary`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-bnrytypes) · `DEFAULT NULL`

    A BLOB containing a photograph of the employee\.

**`EMAIL`**

:   [`VARCHAR(50)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes) · `DEFAULT NULL`

    The staff member email address\.

**`STORE_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    The staff member *home store*\. The employee can work at other stores but is generally assigned to the store listed\.

**`ACTIVE`**

:   [`BOOLEAN`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-booleantypes) · `NOT NULL` · `DEFAULT TRUE`

    Whether this is an active employee\. If employees leave, their rows are not deleted from this table; instead, this column is set to `FALSE`\.

**`USERNAME`**

:   [`VARCHAR(16)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes) · `NOT NULL`

    The user name used by the staff member to access the rental system\.

**`PASSWORD`**

:   [`VARCHAR(40)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes) · `DEFAULT NULL`

    The password used by the staff member to access the rental system\. The password should be stored as a secure hash\.

**`LAST_UPDATE`**

:   [`TIMESTAMP`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-datetime) · `NOT NULL` · `DEFAULT CURRENT_TIMESTAMP`

    When the row was created or most recently updated\.

## Primary key

This table has a primary key.

**`STAFF`**

:   `STAFF_ID`

## Foreign keys

This table has one foreign key.

**`FK_STAFF_ADDRESS`**

:   `ADDRESS_ID` » [`ADDRESS (ADDRESS_ID)`](../../tables/address) · `ON UPDATE CASCADE` · `ON DELETE NO ACTION`

**`FK_STAFF_STORE`**

:   `STORE_ID` » [`STORE (STORE_ID)`](../../tables/store) · `ON UPDATE CASCADE` · `ON DELETE NO ACTION`

## Indices

This table has 5 indices.

**`FK_STAFF_ADDRESS`**

:   `ADDRESS_ID`

**`FK_STAFF_STORE`**

:   `STORE_ID`

**`IDX_STAFF_FK_ADDRESS_ID`**

:   `ADDRESS_ID`

**`IDX_STAFF_FK_STORE_ID`**

:   `STORE_ID`

**`RDB$PRIMARY15`**

:   `STAFF_ID`
