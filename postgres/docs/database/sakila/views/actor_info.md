# View **actor\_info**

This view provides a list of all actors, including the films in which they have performed, broken down by category\. The view incorporates data from the [film](../../tables/film), [actor](../../tables/actor), [category](../../tables/category), [film\_actor](../../tables/film_actor), and [film\_category](../../tables/film_category) tables\.

## Schema

This view belongs to schema [sakila](../../schema).

## Query

??? info "SQL"

    ``` sql
     SELECT a.actor_id,
        a.first_name,
        a.last_name,
        string_agg(DISTINCT concat(c.name, ': ', ( SELECT string_agg((f.title)::text, ', '::text ORDER BY f.title) AS string_agg
               FROM ((sakila.film f
                 JOIN sakila.film_category fc_1 ON ((f.film_id = fc_1.film_id)))
                 JOIN sakila.film_actor fa_1 ON ((f.film_id = fa_1.film_id)))
              WHERE ((fc_1.category_id = c.category_id) AND (fa_1.actor_id = a.actor_id)))), '; '::text) AS film_info
       FROM (((sakila.actor a
         LEFT JOIN sakila.film_actor fa ON ((a.actor_id = fa.actor_id)))
         LEFT JOIN sakila.film_category fc ON ((fa.film_id = fc.film_id)))
         LEFT JOIN sakila.category c ON ((fc.category_id = c.category_id)))
      GROUP BY a.actor_id, a.first_name, a.last_name;
    ```

## Columns

This view contains 4 columns.

**`actor_id`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html)

**`first_name`**

:   [`character varying(45)`](https://www.postgresql.org/docs/current/datatype-character.html)

**`last_name`**

:   [`character varying(45)`](https://www.postgresql.org/docs/current/datatype-character.html)

**`film_info`**

:   [`text`](https://www.postgresql.org/docs/current/datatype-character.html)
