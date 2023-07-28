# Table **FILM\_ACTOR**

This table is used to support a many\-to\-many relationship between films and actors\. For each actor in a given film, there will be one row in the [FILM\_ACTOR](../../tables/film_actor) table listing the actor and film\. The table refers to the [FILM](../../tables/film) and [ACTOR](../../tables/actor) tables using foreign keys\.

## Columns

This table contains 3 columns.

**`ACTOR_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    A foreign key identifying the actor\.

**`FILM_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    A foreign key identifying the film\.

**`LAST_UPDATE`**

:   [`TIMESTAMP`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-datetime) · `NOT NULL` · `DEFAULT CURRENT_TIMESTAMP`

    When the row was created or most recently updated\.

## Primary key

This table has a primary key.

**`FILM_ACTOR`**

:   `ACTOR_ID, FILM_ID`

## Foreign keys

This table has one foreign key.

**`FK_FILM_ACTOR_ACTOR`**

:   `ACTOR_ID` » [`ACTOR (ACTOR_ID)`](../../tables/actor) · `ON UPDATE CASCADE` · `ON DELETE NO ACTION`

**`FK_FILM_ACTOR_FILM`**

:   `FILM_ID` » [`FILM (FILM_ID)`](../../tables/film) · `ON UPDATE CASCADE` · `ON DELETE NO ACTION`

## Indices

This table has 5 indices.

**`FILM_ACTOR_IDX_FK_ACTOR`**

:   `ACTOR_ID`

**`FILM_ACTOR_IDX_FK_FILM`**

:   `FILM_ID`

**`FK_FILM_ACTOR_ACTOR`**

:   `ACTOR_ID`

**`FK_FILM_ACTOR_FILM`**

:   `FILM_ID`

**`RDB$PRIMARY8`**

:   `ACTOR_ID, FILM_ID`
