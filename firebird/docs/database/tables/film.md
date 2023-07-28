# Table **FILM**

This table is a list of all films potentially in stock in the stores\. The actual in\-stock copies of each film are represented in the inventory table\. The table refers to the [LANGUAGE](../../tables/language) table and is referred to by the [FILM\_CATEGORY](../../tables/film_category), [FILM\_ACTOR](../../tables/film_actor), and [INVENTORY](../../tables/inventory) tables\.

## Columns

This table contains 13 columns.

**`FILM_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    A surrogate primary key used to uniquely identify each film in the table\.

**`TITLE`**

:   [`VARCHAR(255)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes) · `NOT NULL`

    The title of the film\.

**`DESCRIPTION`**

:   [`BLOB subtype text`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-bnrytypes) · `DEFAULT NULL`

    A short description or plot summary of the film\.

**`RELEASE_YEAR`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `DEFAULT NULL`

    The year in which the movie was released\.

**`LANGUAGE_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL`

    A foreign key pointing at the [LANGUAGE](../../tables/language) table; identifies the language of the film\.

**`ORIGINAL_LANGUAGE_ID`**

:   [`INTEGER`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `DEFAULT NULL`

    A foreign key pointing at the [LANGUAGE](../../tables/language) table; identifies the original language of the film\. Used when a film has been dubbed into a new language\.

**`RENTAL_DURATION`**

:   [`SMALLINT`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `NOT NULL` · `DEFAULT 3`

    The length of the rental period, in days\.

**`RENTAL_RATE`**

:   [`DECIMAL`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-fixedtypes) · `NOT NULL` · `DEFAULT 4.99`

    The cost to rent the film for the period specified in the `RENTAL_DURATION` column\.

**`LENGTH`**

:   [`SMALLINT`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-inttypes) · `DEFAULT NULL`

    The duration of the film, in minutes\.

**`REPLACEMENT_COST`**

:   [`DECIMAL`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-fixedtypes) · `NOT NULL` · `DEFAULT 19.99`

    The amount charged to the customer if the film is not returned or is returned in a damaged state\.

**`RATING`**

:   [`VARCHAR(5)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes) · `DEFAULT 'G'`

    The rating assigned to the film\. Can be one of: `G`, `PG`, `PG-13`, `R`, or `NC-17`\.

    Value | Description
    - | -
    G | General audiences – All ages admitted\.
    PG | Parental guidance suggested – Some material may not be suitable for children\.
    PG\-13 | Parents strongly cautioned – Some material may be inappropriate for children under 13\.
    R | Restricted – Under 17 requires accompanying parent or adult guardian\.
    NC\-17 | No children under 17 admitted\.

**`SPECIAL_FEATURES`**

:   [`VARCHAR(100)`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-chartypes) · `DEFAULT NULL`

    Lists which common special features are included on the DVD\. Can be zero or more of: `Trailers`, `Commentaries`, `Deleted Scenes`, `Behind the Scenes`\.

**`LAST_UPDATE`**

:   [`TIMESTAMP`](https://firebirdsql.org/file/documentation/html/en/refdocs/fblangref40/firebird-40-language-reference.html#fblangref40-datatypes-datetime) · `NOT NULL` · `DEFAULT CURRENT_TIMESTAMP`

    When the row was created or most recently updated\.

## Primary key

This table has a primary key.

**`FILM`**

:   `FILM_ID`

## Foreign keys

This table has one foreign key.

**`FK_FILM_LANGUAGE`**

:   `LANGUAGE_ID` » [`LANGUAGE (LANGUAGE_ID)`](../../tables/language) · `ON UPDATE CASCADE` · `ON DELETE NO ACTION`

**`FK_FILM_LANGUAGE_ORIGINAL`**

:   `ORIGINAL_LANGUAGE_ID` » [`LANGUAGE (LANGUAGE_ID)`](../../tables/language) · `ON UPDATE CASCADE` · `ON DELETE NO ACTION`

## Indices

This table has 5 indices.

**`FK_FILM_LANGUAGE`**

:   `LANGUAGE_ID`

**`FK_FILM_LANGUAGE_ORIGINAL`**

:   `ORIGINAL_LANGUAGE_ID`

**`IDX_FILM_FK_LANGUAGE_ID`**

:   `LANGUAGE_ID`

**`IDX_FILM_FK_ORIGINAL_LANGUAGE_ID`**

:   `ORIGINAL_LANGUAGE_ID`

**`RDB$PRIMARY7`**

:   `FILM_ID`
