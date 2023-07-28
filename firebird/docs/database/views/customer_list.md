# View **CUSTOMER\_LIST**

This view provides a list of customers, with first name and last name concatenated together and address information combined into a single view\. The view incorporates data from the [CUSTOMER](../../tables/customer), [ADDRESS](../../tables/address), [CITY](../../tables/city), and [COUNTRY](../../tables/country) tables\.

## Query

??? info "SQL"

    ``` sql
    SELECT 
      cu.customer_id AS ID,
      cu.first_name||' '||cu.last_name AS name,
      a.address AS address,
      a.postal_code AS "zip code",
      a.phone AS phone,
      city.city AS city,
      country.country AS country,
      case when cu.active=1 then 'active' else '' end AS notes,
      cu.store_id AS SID
    FROM 
      customer AS cu 
    JOIN  
      address AS a ON cu.address_id = a.address_id 
    JOIN 
      city ON a.city_id = city.city_id
    JOIN 
      country ON city.country_id = country.country_id
    ```

## Columns

This view contains 9 columns.

**`ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes)

**`NAME`**

:   [`VARCHAR(91)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes)

**`ADDRESS`**

:   [`VARCHAR(50)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes)

**`zip code`**

:   [`VARCHAR(10)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes)

**`PHONE`**

:   [`VARCHAR(20)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes)

**`CITY`**

:   [`VARCHAR(50)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes)

**`COUNTRY`**

:   [`VARCHAR(50)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes)

**`NOTES`**

:   [`CHAR(6)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes)

**`SID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes)
