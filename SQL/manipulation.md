# Manipulation

Every clause should be ended with semicolon.

## Operators

-   `CREATE TABLE`.

```sql
CREATE TABLE table_name (
   column_1 data_type,
   column_2 data_type,
   column_3 data_type
);
```

-   `INSERT INTO ... VALUES` adds a new row.

```sql
INSERT INTO celebs (id, name, age)
VALUES (1, 'Random Random', 20);
```

-   `SELECT`.
-   `ALTER TABLE`.
-   `ADD COLUMN`.

```sql
ALTER TABLE celebs
ADD COLUMN new_data TEXT;
```

-   `UPDATE` edits a row.
-   `SET` updates column value in selected row.

```sql
UPDATE table
SET name = 'ololo'
WHERE id = 4;
```

-   `DELETE FROM` deletes rows.

## Constraints

-   `PRIMARY KEY`.
-   `UNIQUE`.
-   `NOT NULL`.
-   `DEFAULT`.
