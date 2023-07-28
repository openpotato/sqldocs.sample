# Table **staff**

This table lists all staff members, including information for email address, login information, and picture\. The table refers to the [store](../../tables/store) and [address](../../tables/address) tables using foreign keys, and is referred to by the [rental](../../tables/rental), [payment](../../tables/payment), and [store](../../tables/store) tables\.

## Schema

This table belongs to schema [sakila](../../schema).

## Columns

This table contains 11 columns.

**`staff_id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    A surrogate primary key that uniquely identifies the staff member\.

**`first_name`**

:   [`character varying(45)`](https://www.postgresql.org/docs/current/datatype-character.html) · `NOT NULL`

    The first name of the staff member\.

**`last_name`**

:   [`character varying(45)`](https://www.postgresql.org/docs/current/datatype-character.html) · `NOT NULL`

    The last name of the staff member\.

**`address_id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    A foreign key to the staff member address in the [address](../../tables/address) table\.

**`picture`**

:   `bytea`

    A BLOB containing a photograph of the employee\.

**`email`**

:   [`character varying(50)`](https://www.postgresql.org/docs/current/datatype-character.html) · `NULL::character varying`

    The staff member email address\.

**`store_id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    The staff member *home store*\. The employee can work at other stores but is generally assigned to the store listed\.

**`active`**

:   [`boolean`](https://www.postgresql.org/docs/current/datatype-boolean.html) · `NOT NULL` · `true`

    Whether this is an active employee\. If employees leave, their rows are not deleted from this table; instead, this column is set to `FALSE`\.

**`username`**

:   [`character varying(16)`](https://www.postgresql.org/docs/current/datatype-character.html) · `NOT NULL`

    The user name used by the staff member to access the rental system\.

**`password`**

:   [`character varying(40)`](https://www.postgresql.org/docs/current/datatype-character.html) · `NULL::character varying`

    The password used by the staff member to access the rental system\. The password should be stored as a secure hash\.

**`last_update`**

:   [`timestamp(0) without time zone`](https://www.postgresql.org/docs/current/datatype-datetime.html) · `NOT NULL` · `CURRENT_TIMESTAMP`

## Primary key

This table has a primary key.

**`staff`**

:   `staff_id`

## Foreign keys

This table has one foreign key.

**`fk_staff_address`**

:   `address_id` » [`sakila.address (address_id)`](../../sakila/tables/address) · `ON UPDATE CASCADE` · `ON DELETE RESTRICT`

**`fk_staff_store`**

:   `store_id` » [`sakila.store (store_id)`](../../sakila/tables/store) · `ON UPDATE CASCADE` · `ON DELETE RESTRICT`

## Indices

This table has 3 indices.

**`staff_pkey`**

:   `staff_id`

**`idx_staff_fk_address_id`**

:   `address_id`

**`idx_staff_fk_store_id`**

:   `store_id`
