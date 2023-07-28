# View **NICER\_BUT\_SLOWER\_FILM\_LIST**

This view contains a formatted view of the [FILM](../../tables/film) table, with a comma\-separated list of the film's actors\. The view differs from the [FILM\_LIST](../../views/film_list) view in the list of actors\. The lettercase of the actor names is adjusted so that the first letter of each name is capitalized, rather than having the name in all\-caps\. As indicated in its name, this view performs additional processing and therefore takes longer to return data than the [FILM\_LIST](../../views/film_list) view\. The view incorporates data from the [FILM](../../tables/film), [CATEGORY](../../tables/category), [FILM\_CATEGORY](../../tables/film_category), [ACTOR](../../tables/actor), and [FILM\_ACTOR](../../tables/film_actor) tables\.

## Query

??? info "SQL"

    ``` sql
    SELECT 
      film.film_id AS FID, 
      film.title AS title, 
      film.description AS description, 
      category.name AS category, 
      film.rental_rate AS price,
      film.length AS length, 
      film.rating AS rating, 
      LIST(
    	UPPER(SUBSTRING(actor.first_name from 1 for 1))||LOWER(SUBSTRING(actor.first_name from 2 for CHAR_LENGTH(actor.first_name)))||' '||
    	UPPER(SUBSTRING(actor.last_name from 1 for 1))||LOWER(SUBSTRING(actor.last_name from 2 for CHAR_LENGTH(actor.last_name))), ', ') AS actors
    FROM 
      film 
    LEFT JOIN 
      film_category ON film_category.film_id = film.film_id
    LEFT JOIN 
      category ON category.category_id = film_category.category_id 
    LEFT JOIN 
      film_actor ON film.film_id = film_actor.film_id 
    LEFT JOIN 
      actor ON film_actor.actor_id = actor.actor_id
    GROUP BY 
      film.film_id, 
      category.name, 
      film.title,
      film.description, 
      film.rental_rate, 
      film.length, 
      film.rating
    ```

## Columns

This view contains 8 columns.

**`FID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes)

**`TITLE`**

:   [`VARCHAR(255)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes)

**`DESCRIPTION`**

:   [`BLOB subtype text`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-bnrytypes)

**`CATEGORY`**

:   [`VARCHAR(25)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes)

**`PRICE`**

:   [`DECIMAL`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-fixedtypes)

**`LENGTH`**

:   [`SMALLINT`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes)

**`RATING`**

:   [`VARCHAR(5)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes)

**`ACTORS`**

:   [`BLOB subtype text`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-bnrytypes)
