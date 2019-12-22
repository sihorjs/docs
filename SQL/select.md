# Select data from SQL

## Operators

-   `SELECT`.
-   `FROM`.
-   `AS` used to rename column of table in query.
-   `DISTINCT` used to return unique values from query.

```sql
SELECT DISTINCT name
FROM tools;
```

-   `WHERE` used to set condition and filter results.
-   `LIKE` used to filter data by pattern.
-   `IS NULL` and `IS NOT NULL`.
-   `BETWEEN` used to select range.
-   `AND`.
-   `OR`.
-   `ORDER BY` used to sort data. Goes always after `WHERE`. Can specify `ASC` (default) or `DESC` sorting order.

```sql
SELECT *
FROM movies
ORDER BY year DESC;
```

-   `LIMIT`.
-   `CASE` - used to query different data depending on input.

```sql
SELECT name,
CASE
    WHEN imdb_rating > 8 THEN 'Cool'
    -- Default clause
    ELSE 'Bad'
END AS 'Rated films';
```

## Comparison

-   `=`.
-   `>`, `<`, `>=`, ... .

## Wildcards

-   `*`.
-   `_` matches any character in `LIKE` clause.
-   `%` matches zero or more missing letters in the pattern.

```sql
SELECT *
LIKE %man%
FROM movies;
```
