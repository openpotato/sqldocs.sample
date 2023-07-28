# View **STAFF\_LIST**

This view provides a list of all staff members, including address and store information\. The view incorporates data from the [STAFF](../../tables/staff) and [ADDRESS](../../tables/address) tables\.

## Query

??? info "SQL"

    ``` sql
    SELECT 
      s.staff_id AS ID,
      s.first_name||' '||s.last_name AS name, 
      a.address AS address, 
      a.postal_code AS "zip code",
      a.phone AS phone,
      city.city AS city, 
      country.country AS country, 
      s.store_id AS SID
    FROM 
      staff AS s 
    JOIN 
      address AS a ON s.address_id = a.address_id 
    JOIN 
      city ON a.city_id = city.city_id
    JOIN 
      country ON city.country_id = country.country_id
    ```

## Columns

This view contains 8 columns.

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

**`SID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes)
