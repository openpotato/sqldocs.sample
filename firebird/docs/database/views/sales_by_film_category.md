# View **SALES\_BY\_FILM\_CATEGORY**

This view provides a list of total sales, broken down by individual film category\. Because a film can be listed in multiple categories, it is not advisable to calculate aggregate sales by totalling the rows of this view\. The view incorporates data from the [CATEGORY](../../tables/category), [PAYMENT](../../tables/payment), [RENTAL](../../tables/rental), [INVENTORY](../../tables/inventory), [FILM](../../tables/film), [FILM\_CATEGORY](../../tables/film_category), and [CATEGORY](../../tables/category) tables\.

## Query

??? info "SQL"

    ``` sql
    SELECT
      c.name AS category, 
      SUM(p.amount) AS total_sales
    FROM 
      payment AS p
    INNER JOIN 
      rental AS r ON p.rental_id = r.rental_id
    INNER JOIN 
      inventory AS i ON r.inventory_id = i.inventory_id
    INNER JOIN 
      film AS f ON i.film_id = f.film_id
    INNER JOIN 
      film_category AS fc ON f.film_id = fc.film_id
    INNER JOIN 
      category AS c ON fc.category_id = c.category_id
    GROUP BY 
      c.name
    ORDER BY 
      total_sales DESC
    ```

## Columns

This view contains 2 columns.

**`CATEGORY`**

:   [`VARCHAR(25)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes)

**`TOTAL_SALES`**

:   [`DECIMAL`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-fixedtypes)
