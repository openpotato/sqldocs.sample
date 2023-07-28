# Table **rental**

This table contains one row for each rental of each inventory item with information about who rented what item, when it was rented, and when it was returned\. The table refers to the [inventory](../../tables/inventory), [customer](../../tables/customer), and [staff](../../tables/staff) tables and is referred to by the [payment](../../tables/payment) table\.

## Schema

This table belongs to schema [sakila](../../schema).

## Columns

This table contains 7 columns.

**`rental_id`**

:   [`integer`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    A surrogate primary key that uniquely identifies the rental\.

**`rental_date`**

:   [`timestamp(0) without time zone`](https://www.postgresql.org/docs/current/datatype-datetime.html) · `NOT NULL`

    The date and time that the item was rented\.

**`inventory_id`**

:   [`integer`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    The item being rented\.

**`customer_id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    The customer renting the item\.

**`return_date`**

:   [`timestamp(0) without time zone`](https://www.postgresql.org/docs/current/datatype-datetime.html) · `NULL::timestamp without time zone`

    The date and time the item was returned\.

**`staff_id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    The staff member who processed the rental\.

**`last_update`**

:   [`timestamp(0) without time zone`](https://www.postgresql.org/docs/current/datatype-datetime.html) · `NOT NULL` · `CURRENT_TIMESTAMP`

    When the row was created or most recently updated\.

## Primary key

This table has a primary key.

**`rental`**

:   `rental_id`

## Foreign keys

This table has one foreign key.

**`fk_rental_customer`**

:   `customer_id` » [`sakila.customer (customer_id)`](../../sakila/tables/customer) · `ON UPDATE CASCADE` · `ON DELETE RESTRICT`

**`fk_rental_inventory`**

:   `inventory_id` » [`sakila.inventory (inventory_id)`](../../sakila/tables/inventory) · `ON UPDATE CASCADE` · `ON DELETE RESTRICT`

**`fk_rental_staff`**

:   `staff_id` » [`sakila.staff (staff_id)`](../../sakila/tables/staff) · `ON UPDATE CASCADE` · `ON DELETE RESTRICT`

## Indices

This table has 5 indices.

**`rental_pkey`**

:   `rental_id`

**`idx_rental_fk_customer_id`**

:   `customer_id`

**`idx_rental_fk_inventory_id`**

:   `inventory_id`

**`idx_rental_fk_staff_id`**

:   `staff_id`

**`rental_rental_date_inventory_id_customer_id_key`**

:   `rental_date, inventory_id, customer_id`
