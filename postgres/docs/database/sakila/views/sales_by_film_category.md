# View **sales\_by\_film\_category**

This view provides a list of total sales, broken down by individual film category\. Because a film can be listed in multiple categories, it is not advisable to calculate aggregate sales by totalling the rows of this view\. The view incorporates data from the [category](../../tables/category), [payment](../../tables/payment), [rental](../../tables/rental), [inventory](../../tables/inventory), [film](../../tables/film), [film\_category](../../tables/film_category), and [category](../../tables/category) tables\.

## Schema

This view belongs to schema [sakila](../../schema).

## Query

??? info "SQL"

    ``` sql
     SELECT c.name AS category,
        sum(p.amount) AS total_sales
       FROM (((((sakila.payment p
         JOIN sakila.rental r ON ((p.rental_id = r.rental_id)))
         JOIN sakila.inventory i ON ((r.inventory_id = i.inventory_id)))
         JOIN sakila.film f ON ((i.film_id = f.film_id)))
         JOIN sakila.film_category fc ON ((f.film_id = fc.film_id)))
         JOIN sakila.category c ON ((fc.category_id = c.category_id)))
      GROUP BY c.name
      ORDER BY (sum(p.amount)) DESC;
    ```

## Columns

This view contains 2 columns.

**`category`**

:   [`character varying(25)`](https://www.postgresql.org/docs/current/datatype-character.html)

**`total_sales`**

:   [`numeric`](https://www.postgresql.org/docs/current/datatype-numeric.html)
