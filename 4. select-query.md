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

#### Get all rows from a DB table:

```
SELECT * FROM app_user;
```

#### Result:
```
id |  username   |         email          |       name       |         created_at         
----+-------------+------------------------+------------------+----------------------------
  1 | devadmin2   | devadmin2@gmail.com    | Md Nazmul Hasan  | 2021-09-20 06:56:20.022758
  2 | devadmin    | devadmin@gmail.com     | Md Nazmul Hasan  | 2021-09-20 06:56:20.022758
  3 | farzana     | niloy@gmail.com        | Farzana Yesmin   | 2021-09-20 06:56:20.022758
  4 | hasan08sust | nazmul.hasan@gmail.com | Nazmul Hasan     | 2021-09-20 06:56:20.022758
  5 | salma       | salma.ummay@gmail.com  | Ummay Salma      | 2021-09-20 06:56:20.022758
  6 | devadmin2   | devadmin2@gmail.com    | Mr. Nazmul Hasan | 2021-09-20 06:56:20.022758
(6 rows)
```

#### Select some specific fields:

```
SELECT id, username, name from app_user;
```

#### Result:

```
id |  username   |       name       
----+-------------+------------------
  1 | devadmin2   | Md Nazmul Hasan
  2 | devadmin    | Md Nazmul Hasan
  3 | farzana     | Farzana Yesmin
  4 | hasan08sust | Nazmul Hasan
  5 | salma       | Ummay Salma
  6 | devadmin2   | Mr. Nazmul Hasan
(6 rows)
```