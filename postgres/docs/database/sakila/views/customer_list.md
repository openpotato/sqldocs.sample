# View **customer\_list**

This view provides a list of customers, with first name and last name concatenated together and address information combined into a single view\. The view incorporates data from the [customer](../../tables/customer), [address](../../tables/address), [city](../../tables/city), and [country](../../tables/country) tables\.

## Schema

This view belongs to schema [sakila](../../schema).

## Query

??? info "SQL"

    ``` sql
     SELECT cu.customer_id AS id,
        concat((cu.first_name)::text, ' '::text, (cu.last_name)::text) AS name,
        a.address,
        a.postal_code AS "zip code",
        a.phone,
        city.city,
        country.country,
            CASE
                WHEN cu.active THEN 'active'::text
                ELSE ''::text
            END AS notes,
        cu.store_id AS sid
       FROM (((sakila.customer cu
         JOIN sakila.address a ON ((cu.address_id = a.address_id)))
         JOIN sakila.city ON ((a.city_id = city.city_id)))
         JOIN sakila.country ON ((city.country_id = country.country_id)));
    ```

## Columns

This view contains 9 columns.

**`id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html)

**`name`**

:   [`text`](https://www.postgresql.org/docs/current/datatype-character.html)

**`address`**

:   [`character varying(50)`](https://www.postgresql.org/docs/current/datatype-character.html)

**`zip code`**

:   [`character varying(10)`](https://www.postgresql.org/docs/current/datatype-character.html)

**`phone`**

:   [`character varying(20)`](https://www.postgresql.org/docs/current/datatype-character.html)

**`city`**

:   [`character varying(50)`](https://www.postgresql.org/docs/current/datatype-character.html)

**`country`**

:   [`character varying(50)`](https://www.postgresql.org/docs/current/datatype-character.html)

**`notes`**

:   [`text`](https://www.postgresql.org/docs/current/datatype-character.html)

**`sid`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html)
