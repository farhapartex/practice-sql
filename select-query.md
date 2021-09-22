### SELECT Query

The following illustrates the basic syntax of the SELECT statement that retrieves data from a single table.

```
SELECT 
    select_list
FROM
    table_name;
```

#### Get table list by command
```
\dt
```

#### Get system tables live in the pg_catalog database.
```
SELECT * FROM pg_catalog.pg_tables;
```