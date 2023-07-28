# Table **payment**

This table records each payment made by a customer, with information such as the amount and the rental being paid for \(when applicable\)\. The table refers to the [customer](../../tables/customer), [rental](../../tables/rental), and [staff](../../tables/staff) table\.

## Schema

This table belongs to schema [sakila](../../schema).

## Columns

This table contains 7 columns.

**`payment_id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    A surrogate primary key used to uniquely identify each payment\.

**`customer_id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    The customer whose balance the payment is being applied to\. This is a foreign key reference to the [customer](../../tables/customer) table\.

**`staff_id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    The staff member who processed the payment\. This is a foreign key reference to the [staff](../../tables/staff) table\.

**`rental_id`**

:   [`integer`](https://www.postgresql.org/docs/current/datatype-numeric.html)

    The rental that the payment is being applied to\. This is optional because some payments are for outstanding fees and may not be directly related to a rental\.

**`amount`**

:   [`numeric(5,2)`](https://www.postgresql.org/docs/current/datatype-numeric.html) · `NOT NULL`

    The amount of the payment\.

**`payment_date`**

:   [`timestamp(0) without time zone`](https://www.postgresql.org/docs/current/datatype-datetime.html) · `NOT NULL`

    The date the payment was processed\.

**`last_update`**

:   [`timestamp(0) without time zone`](https://www.postgresql.org/docs/current/datatype-datetime.html) · `CURRENT_TIMESTAMP`

    When the row was created or most recently updated\.

## Primary key

This table has a primary key.

**`payment`**

:   `payment_id`

## Foreign keys

This table has one foreign key.

**`fk_payment_customer`**

:   `customer_id` » [`sakila.customer (customer_id)`](../../sakila/tables/customer) · `ON UPDATE CASCADE` · `ON DELETE RESTRICT`

**`fk_payment_rental`**

:   `rental_id` » [`sakila.rental (rental_id)`](../../sakila/tables/rental) · `ON UPDATE CASCADE` · `ON DELETE SET NULL`

**`fk_payment_staff`**

:   `staff_id` » [`sakila.staff (staff_id)`](../../sakila/tables/staff) · `ON UPDATE CASCADE` · `ON DELETE RESTRICT`

## Indices

This table has 3 indices.

**`payment_pkey`**

:   `payment_id`

**`idx_payment_fk_customer_id`**

:   `customer_id`

**`idx_payment_fk_staff_id`**

:   `staff_id`
