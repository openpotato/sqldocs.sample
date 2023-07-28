# View **SALES\_BY\_STORE**

This view provides a list of total sales, broken down by store\. The view returns the store location, manager name, and total sales\. The view incorporates data from the [CITY](../../tables/city), [COUNTRY](../../tables/country), [PAYMENT](../../tables/payment), [RENTAL](../../tables/rental), [INVENTORY](../../tables/inventory), [STORE](../../tables/store), [ADDRESS](../../tables/address), and [STAFF](../../tables/staff) tables\.

## Query

??? info "SQL"

    ``` sql
    SELECT
      c.city||','||cy.country AS store,
      m.first_name||' '||m.last_name AS manager,
      SUM(p.amount) AS total_sales
    FROM 
      payment AS p
    INNER JOIN 
      rental AS r ON p.rental_id = r.rental_id
    INNER JOIN 
      inventory AS i ON r.inventory_id = i.inventory_id
    INNER JOIN 
      store AS s ON i.store_id = s.store_id
    INNER JOIN 
      address AS a ON s.address_id = a.address_id
    INNER JOIN 
      city AS c ON a.city_id = c.city_id
    INNER JOIN 
      country AS cy ON c.country_id = cy.country_id
    INNER JOIN 
      staff AS m ON s.manager_staff_id = m.staff_id
    GROUP BY 
      s.store_id, store, manager
    ```

## Columns

This view contains 3 columns.

**`STORE`**

:   [`VARCHAR(101)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes)

**`MANAGER`**

:   [`VARCHAR(91)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes)

**`TOTAL_SALES`**

:   [`DECIMAL`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-fixedtypes)
