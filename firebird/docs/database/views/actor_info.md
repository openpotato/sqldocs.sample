# View **ACTOR\_INFO**

This view provides a list of all actors, including the films in which they have performed, broken down by category\. The view incorporates data from the [FILM](../../tables/film), [ACTOR](../../tables/actor), [CATEGORY](../../tables/category), [FILM\_ACTOR](../../tables/film_actor), and [FILM\_CATEGORY](../../tables/film_category) tables\.

## Query

??? info "SQL"

    ``` sql
    SELECT
      a.actor_id,
      a.first_name,
      a.last_name,
      LIST(
        c.name||': '||(
    	  SELECT 
    	    LIST(f.title, ', ')
          FROM 
    	    film f
          INNER JOIN 
    	    film_category fc ON f.film_id = fc.film_id
          INNER JOIN 
    	    film_actor fa ON f.film_id = fa.film_id
          WHERE 
    	    fc.category_id = c.category_id AND fa.actor_id = a.actor_id
        ), '; ') AS film_info
    FROM 
      actor a
    LEFT JOIN 
      film_actor fa ON a.actor_id = fa.actor_id
    LEFT JOIN 
      film_category fc ON fa.film_id = fc.film_id
    LEFT JOIN 
      category c ON fc.category_id = c.category_id
    GROUP BY 
      a.actor_id, a.first_name, a.last_name
    ```

## Columns

This view contains 4 columns.

**`ACTOR_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes)

**`FIRST_NAME`**

:   [`VARCHAR(45)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes)

**`LAST_NAME`**

:   [`VARCHAR(45)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes)

**`FILM_INFO`**

:   [`BLOB subtype text`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-bnrytypes)
