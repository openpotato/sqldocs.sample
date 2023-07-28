# Table **store**

This table lists all stores in the system\. All inventory is assigned to specific stores, and staff and customers are assigned a *home store*\. The table refers to the [STAFF](../../tables/staff) and [ADDRESS](../../tables/address) tables using foreign keys and is referred to by the [STAFF](../../tables/staff), [CUSTOMER](../../tables/customer), and [INVENTORY](../../tables/inventory) tables\.

## Schema

This table belongs to schema [sakila](../../schema).

## Columns

This table contains 4 columns.

**`store_id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    A surrogate primary key that uniquely identifies the store\.

**`manager_staff_id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    A foreign key identifying the manager of this store\.

**`address_id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    A foreign key identifying the address of this store\.

**`last_update`**

:   [`timestamp(0) without time zone`](https://www.postgresql.org/docs/current/datatype-datetime.html) · `NOT NULL` · `CURRENT_TIMESTAMP`

    When the row was created or most recently updated\.

## Primary key

This table has a primary key.

**`store`**

:   `store_id`

## Foreign keys

This table has one foreign key.

**`fk_store_address`**

:   `address_id` » [`sakila.address (address_id)`](../../sakila/tables/address) · `ON UPDATE CASCADE` · `ON DELETE RESTRICT`

**`fk_store_staff`**

:   `manager_staff_id` » [`sakila.staff (staff_id)`](../../sakila/tables/staff) · `ON UPDATE CASCADE` · `ON DELETE RESTRICT`

## Indices

This table has 3 indices.

**`store_pkey`**

:   `store_id`

**`idx_store_fk_address_id`**

:   `address_id`

**`store_manager_staff_id_key`**

:   `manager_staff_id`
