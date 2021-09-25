### Introduction to SQL LIMIT clause

To retrieve a portion of rows returned by a query, you use the LIMIT and OFFSET clauses. The following illustrates the syntax of these clauses:

```
SELECT 
    column_list
FROM
    table1
ORDER BY column_list
LIMIT row_count OFFSET offset;
```

In this syntax:

* The row_count determines the number of rows that will be returned.
* The OFFSET  clause skips the offset rows before beginning to return the rows. The OFFSET clause is optional so you can skip it. If you use both LIMIT and OFFSET clauses the OFFSET  skips offset rows first before the LIMIT  constrains the number of rows.

```
When you use the LIMIT clause, it is important to use an ORDER BY clause to make sure that the rows in the returned are in a specified order.
```

```
Not all database systems support the LIMIT clause, therefore, the LIMIT clause is available only in some database systems only such as MySQL, PostgreSQL, SQLite, Sybase SQL Anywhere, and HSQLDB.
```

### SQL LIMIT clause examples

All rows

```
SELECT * FROM app_user;
```

Result:

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

Query Using Limit clause

```
SELECT * FROM app_user LIMIT 3;
```

```
id | username  |        email        |      name       |         created_at         
----+-----------+---------------------+-----------------+----------------------------
  1 | devadmin2 | devadmin2@gmail.com | Md Nazmul Hasan | 2021-09-20 06:56:20.022758
  2 | devadmin  | devadmin@gmail.com  | Md Nazmul Hasan | 2021-09-20 06:56:20.022758
  3 | farzana   | niloy@gmail.com     | Farzana Yesmin  | 2021-09-20 06:56:20.022758
(3 rows
```


#### OFFSET Clause

To skip first two rows and get the next three rows, you use both LIMIT and OFFSET clauses as shown in the following statement.
```
SELECT * FROM app_user LIMIT 3 OFFSET 2;
```

```
 id |  username   |         email          |      name      |         created_at         
----+-------------+------------------------+----------------+----------------------------
  3 | farzana     | niloy@gmail.com        | Farzana Yesmin | 2021-09-20 06:56:20.022758
  4 | hasan08sust | nazmul.hasan@gmail.com | Nazmul Hasan   | 2021-09-20 06:56:20.022758
  5 | salma       | salma.ummay@gmail.com  | Ummay Salma    | 2021-09-20 06:56:20.022758
(3 rows)
```