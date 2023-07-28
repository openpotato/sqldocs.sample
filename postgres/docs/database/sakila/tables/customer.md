# Table **customer**

This table contains a list of all customers\.<br>The table is referred to in the [payment](../../tables/payment) and [rental](../../tables/rental) tables and refers to the [address](../../tables/address) and [store](../../tables/store) tables using foreign keys\.

## Schema

This table belongs to schema [sakila](../../schema).

## Columns

This table contains 9 columns.

**`customer_id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    A surrogate primary key used to uniquely identify each customer in the table\.

**`store_id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    A foreign key identifying the customer *home store*\. Customers are not limited to renting only from this store, but this is the store at which they generally shop\.

**`first_name`**

:   [`character varying(45)`](https://www.postgresql.org/docs/current/datatype-character.html) · `NOT NULL`

    The customer first name\.

**`last_name`**

:   [`character varying(45)`](https://www.postgresql.org/docs/current/datatype-character.html) · `NOT NULL`

    The customer last name\.

**`email`**

:   [`character varying(50)`](https://www.postgresql.org/docs/current/datatype-character.html) · `NULL::character varying`

    The customer email address\.

**`address_id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    A foreign key identifying the customer address in the [address](../../tables/address) table\.

**`active`**

:   [`boolean`](https://www.postgresql.org/docs/current/datatype-boolean.html) · `NOT NULL` · `true`

    Indicates whether the customer is an active customer\. Setting this to `FALSE` serves <br> as an alternative to deleting a customer outright\. Most queries should have a `WHERE active = TRUE` clause\.

**`create_date`**

:   [`timestamp(0) without time zone`](https://www.postgresql.org/docs/current/datatype-datetime.html) · `NOT NULL`

    The date the customer was added to the system\. This date is automatically set using a trigger during an `INSERT`\.

**`last_update`**

:   [`timestamp(0) without time zone`](https://www.postgresql.org/docs/current/datatype-datetime.html) · `CURRENT_TIMESTAMP`

    When the row was created or most recently updated\.

## Primary key

This table has a primary key.

**`customer`**

:   `customer_id`

## Foreign keys

This table has one foreign key.

**`fk_customer_address`**

:   `address_id` » [`sakila.address (address_id)`](../../sakila/tables/address) · `ON UPDATE CASCADE` · `ON DELETE RESTRICT`

**`fk_customer_store`**

:   `store_id` » [`sakila.store (store_id)`](../../sakila/tables/store) · `ON UPDATE CASCADE` · `ON DELETE RESTRICT`

## Indices

This table has 4 indices.

**`customer_pkey`**

:   `customer_id`

**`idx_customer_fk_address_id`**

:   `address_id`

**`idx_customer_fk_store_id`**

:   `store_id`

**`idx_customer_last_name`**

:   `last_name`
