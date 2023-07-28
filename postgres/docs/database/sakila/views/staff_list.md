# View **staff\_list**

This view provides a list of all staff members, including address and store information\. The view incorporates data from the [staff](../../tables/staff) and [address](../../tables/address) tables\.

## Schema

This view belongs to schema [sakila](../../schema).

## Query

??? info "SQL"

    ``` sql
     SELECT s.staff_id AS id,
        concat((s.first_name)::text, ' '::text, (s.last_name)::text) AS name,
        a.address,
        a.postal_code AS "zip code",
        a.phone,
        city.city,
        country.country,
        s.store_id AS sid
       FROM (((sakila.staff s
         JOIN sakila.address a ON ((s.address_id = a.address_id)))
         JOIN sakila.city ON ((a.city_id = city.city_id)))
         JOIN sakila.country ON ((city.country_id = country.country_id)));
    ```

## Columns

This view contains 8 columns.

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

**`sid`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html)
