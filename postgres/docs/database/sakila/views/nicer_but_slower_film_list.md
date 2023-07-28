# View **nicer\_but\_slower\_film\_list**

This view contains a formatted view of the [FILM](../../tables/film) table, with a comma\-separated list of the film's actors\. The view differs from the [film\_list](../../views/film_list) view in the list of actors\. The lettercase of the actor names is adjusted so that the first letter of each name is capitalized, rather than having the name in all\-caps\. As indicated in its name, this view performs additional processing and therefore takes longer to return data than the [film\_list](../../views/film_list) view\. The view incorporates data from the [film](../../tables/film), [category](../../tables/category), [film\_category](../../tables/film_category), [actor](../../tables/actor), and [film\_actor](../../tables/film_actor) tables\.

## Schema

This view belongs to schema [sakila](../../schema).

## Query

??? info "SQL"

    ``` sql
     SELECT film.film_id AS fid,
        film.title,
        film.description,
        category.name AS category,
        film.rental_rate AS price,
        film.length,
        film.rating,
        string_agg(concat(concat(upper("substring"((actor.first_name)::text, 1, 1)), lower("substring"((actor.first_name)::text, 2, length((actor.first_name)::text))), ' '::text, concat(upper("substring"((actor.last_name)::text, 1, 1)), lower("substring"((actor.last_name)::text, 2, length((actor.last_name)::text)))))), ', '::text) AS actors
       FROM ((((sakila.film
         LEFT JOIN sakila.film_category ON ((film_category.film_id = film.film_id)))
         LEFT JOIN sakila.category ON ((category.category_id = film_category.category_id)))
         LEFT JOIN sakila.film_actor ON ((film.film_id = film_actor.film_id)))
         LEFT JOIN sakila.actor ON ((film_actor.actor_id = actor.actor_id)))
      GROUP BY film.film_id, category.name;
    ```

## Columns

This view contains 8 columns.

**`fid`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html)

**`title`**

:   [`character varying(128)`](https://www.postgresql.org/docs/current/datatype-character.html)

**`description`**

:   [`text`](https://www.postgresql.org/docs/current/datatype-character.html)

**`category`**

:   [`character varying(25)`](https://www.postgresql.org/docs/current/datatype-character.html)

**`price`**

:   [`numeric(4,2)`](https://www.postgresql.org/docs/current/datatype-numeric.html)

**`length`**

:   [`smallint`](https://www.postgresql.org/docs/current/datatype-numeric.html)

**`rating`**

:   `sakila.rating`

**`actors`**

:   [`text`](https://www.postgresql.org/docs/current/datatype-character.html)
