#### PostgreSQL CREATE TABLE syntax

A relational database consists of multiple related tables. A table consists of rows and columns. Tables allow you to store structured data like customers, products, employees, etc.

To create a new table, you use the `CREATE TABLE` statement. The following illustrates the basic syntax of the `CREATE TABLE` statement:

```
CREATE TABLE [IF NOT EXISTS] table_name (
   column1 datatype(length) column_contraint,
   column2 datatype(length) column_contraint,
   column3 datatype(length) column_contraint,
   table_constraints
);
```

#### Constraints
PostgreSQL includes the following column constraints:

* NOT NULL – ensures that values in a column cannot be NULL.
* UNIQUE – ensures the values in a column unique across the rows within the same table.
* PRIMARY KEY – a primary key column uniquely identify rows in a table. A table can have one and only one primary key. The primary key constraint allows you  to define the primary key of a table.
* CHECK – a CHECK constraint ensures the data must satisfy a boolean expression.
* FOREIGN KEY – ensures values in a column or a group of columns from a table exists in a column or group of columns in another table. Unlike the primary key, a table can have many foreign keys.


#### Example:

Create a test table first:

```
CREATE TABLE IF NOT EXISTS Test (id bigint NOT NULL, name VARCHAR (255) NOT NULL, PRIMARY KEY(id));
```


Create a User table and change the ownership

```
CREATE TABLE IF NOT EXISTS app_user (
	id bigint NOT NULL,
	username VARCHAR ( 50 ) UNIQUE NOT NULL,
	password VARCHAR ( 50 ) NOT NULL,
	email VARCHAR ( 255 ) UNIQUE NOT NULL,
	created_on TIMESTAMP NOT NULL,
    last_login TIMESTAMP,
    PRIMARY KEY (id) 
);

ALTER TABLE app_user OWNER to devadmin;
```