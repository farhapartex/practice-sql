### Introduction to SQL DISTINCT operator

The primary key ensures that the table has no duplicate rows. However, when you use the SELECT statement to query a portion of the columns in a table, you may get duplicates. To remove duplicates from a result set, you use the DISTINCT operator in the SELECT clause as follows:

```
SELECT DISTINCT
    column1, column2, ...
FROM
    table1;
```

If you use one column after the DISTINCT operator, the database system uses that column to evaluate duplicate. In case you use two or more columns, the database system will use the combination of value in these columns for the duplication check. To remove the duplicates, the database system first sorts the result set by every column specified in the SELECT clause. It then scans the table from top to bottom to identify the duplicates that are next to each other. In case the result set is large, the sorting and scanning operations may reduce the performance of the query. 

#### Some Examples:

```
SELECT DISTINCT name from app_user;
```

       name       
------------------
 Md Nazmul Hasan
 Ummay Salma
 Farzana Yesmin
 Mr. Nazmul Hasan
 Nazmul Hasan
(5 rows)


```
SELECT DISTINCT id, name from app_user ORDER BY name;
```

 id |       name       
----+------------------
  3 | Farzana Yesmin
  1 | Md Nazmul Hasan
  2 | Md Nazmul Hasan
  6 | Mr. Nazmul Hasan
  4 | Nazmul Hasan
  5 | Ummay Salma
(6 rows)


#### SQL DISTINCT and NULL values

In the database world, NULL is special. NULL values are used as markers to indicate that the information is missing or not applicable.

For this reason, NULL cannot be compared to any value. Even NULL is not equal to itself. If you have two or more NULL values in a column, does the database system consider them as the same or distinct values?

Typically, the DISTINCT operator treats all NULL values the same. As a result, the DISTINCT operator keeps only one NULL value and removes the other from the result set.

For example, the following statement returns the distinct phone numbers of employees.

```
SELECT DISTINCT
	phone_number
FROM
	employees;
```

