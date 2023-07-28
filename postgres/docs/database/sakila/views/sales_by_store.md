# View **sales\_by\_store**

This view provides a list of total sales, broken down by store\. The view returns the store location, manager name, and total sales\. The view incorporates data from the [CITY](../../tables/city), [COUNTRY](../../tables/country), [PAYMENT](../../tables/payment), [RENTAL](../../tables/rental), [INVENTORY](../../tables/inventory), [STORE](../../tables/store), [ADDRESS](../../tables/address), and [STAFF](../../tables/staff) tables\.

## Schema

This view belongs to schema [sakila](../../schema).

## Query

??? info "SQL"

    ``` sql
     SELECT concat((c.city)::text, ','::text, (cy.country)::text) AS store,
        concat((m.first_name)::text, ' '::text, (m.last_name)::text) AS manager,
        sum(p.amount) AS total_sales
       FROM (((((((sakila.payment p
         JOIN sakila.rental r ON ((p.rental_id = r.rental_id)))
         JOIN sakila.inventory i ON ((r.inventory_id = i.inventory_id)))
         JOIN sakila.store s ON ((i.store_id = s.store_id)))
         JOIN sakila.address a ON ((s.address_id = a.address_id)))
         JOIN sakila.city c ON ((a.city_id = c.city_id)))
         JOIN sakila.country cy ON ((c.country_id = cy.country_id)))
         JOIN sakila.staff m ON ((s.manager_staff_id = m.staff_id)))
      GROUP BY cy.country, c.city, s.store_id, m.first_name, m.last_name
      ORDER BY cy.country, c.city;
    ```

## Columns

This view contains 3 columns.

**`store`**

:   [`text`](https://www.postgresql.org/docs/current/datatype-character.html)

**`manager`**

:   [`text`](https://www.postgresql.org/docs/current/datatype-character.html)

**`total_sales`**

:   [`numeric`](https://www.postgresql.org/docs/current/datatype-numeric.html)
