### Introduction to SQL ORDER BY clause

To specify exactly the order of rows in the result set, you add use an ORDER BY clause in the SELECT statement as follows:

```
SELECT 
    column1, column2
FROM
    table_name
ORDER BY column1 ASC , 
         column2 DESC;
```

In this syntax, the `ORDER BY` clause appears after the `FROM` clause. In case the `SELECT` statement contains a `WHERE` clause, the `ORDER BY` clause must appear after the `WHERE` clause.

To sort the result set, you specify the column in which you want to sort and the kind of the sort order:

* Ascending ( ASC)
* Descending ( DESC)

If you don’t specify the sort order, the database system typically sorts the result set in ascending order `( ASC)` by default.

```
When you include more than one column in the ORDER BY clause, the database system first sorts the result set based on the first column and then sort the sorted result set based on the second column, and so on.
```

#### Example SQL:

#### Example 1

```
SELECT id, name, username from app_user ORDER BY id, name;
```

#### Result:

```
id |       name       |  username   
----+------------------+-------------
  1 | Md Nazmul Hasan  | devadmin2
  2 | Md Nazmul Hasan  | devadmin
  3 | Farzana Yesmin   | farzana
  4 | Nazmul Hasan     | hasan08sust
  5 | Ummay Salma      | salma
  6 | Mr. Nazmul Hasan | devadmin2
(6 rows)
```


#### Example 2:

```
SELECT id, name, username from app_user ORDER BY id DESC, name;
```

#### Result:

```
id |       name       |  username   
----+------------------+-------------
  6 | Mr. Nazmul Hasan | devadmin2
  5 | Ummay Salma      | salma
  4 | Nazmul Hasan     | hasan08sust
  3 | Farzana Yesmin   | farzana
  2 | Md Nazmul Hasan  | devadmin
  1 | Md Nazmul Hasan  | devadmin2
(6 rows)
```