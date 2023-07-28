# Table **PAYMENT**

This table records each payment made by a customer, with information such as the amount and the rental being paid for \(when applicable\)\. The table refers to the [CUSTOMER](../../tables/customer), [RENTAL](../../tables/rental), and [STAFF](../../tables/staff) table\.

## Columns

This table contains 7 columns.

**`PAYMENT_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    A surrogate primary key used to uniquely identify each payment\.

**`CUSTOMER_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    The customer whose balance the payment is being applied to\. This is a foreign key reference to the [CUSTOMER](../../tables/customer) table\.

**`STAFF_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    The staff member who processed the payment\. This is a foreign key reference to the [STAFF](../../tables/staff) table\.

**`RENTAL_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `DEFAULT NULL`

    The rental that the payment is being applied to\. This is optional because some payments are for outstanding fees and may not be directly related to a rental\.

**`AMOUNT`**

:   [`DECIMAL`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-fixedtypes) · `NOT NULL`

    The amount of the payment\.

**`PAYMENT_DATE`**

:   [`TIMESTAMP`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-datetime) · `NOT NULL`

    The date the payment was processed\.

**`LAST_UPDATE`**

:   [`TIMESTAMP`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-datetime) · `NOT NULL` · `DEFAULT CURRENT_TIMESTAMP`

    When the row was created or most recently updated\.

## Primary key

This table has a primary key.

**`PAYMENT`**

:   `PAYMENT_ID`

## Foreign keys

This table has one foreign key.

**`FK_PAYMENT_CUSTOMER`**

:   `CUSTOMER_ID` » [`CUSTOMER (CUSTOMER_ID)`](../../tables/customer) · `ON UPDATE CASCADE` · `ON DELETE NO ACTION`

**`FK_PAYMENT_RENTAL`**

:   `RENTAL_ID` » [`RENTAL (RENTAL_ID)`](../../tables/rental) · `ON UPDATE CASCADE` · `ON DELETE SET NULL`

**`FK_PAYMENT_STAFF`**

:   `STAFF_ID` » [`STAFF (STAFF_ID)`](../../tables/staff) · `ON UPDATE CASCADE` · `ON DELETE NO ACTION`

## Indices

This table has 6 indices.

**`FK_PAYMENT_CUSTOMER`**

:   `CUSTOMER_ID`

**`FK_PAYMENT_RENTAL`**

:   `RENTAL_ID`

**`FK_PAYMENT_STAFF`**

:   `STAFF_ID`

**`IDX_PAYMENT_FK_CUSTOMER_ID`**

:   `CUSTOMER_ID`

**`IDX_PAYMENT_FK_STAFF_ID`**

:   `STAFF_ID`

**`RDB$PRIMARY13`**

:   `PAYMENT_ID`
