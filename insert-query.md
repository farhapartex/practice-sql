### INSERT Query

#### To add data in a single new row, command is like below (Here I use this for app_user table)

```

INSERT INTO app_user(username, email, name, created_at) VALUES('devadmin', 'devadmin@gmail.com', 'Md Nazmul Hasan', '2021-09-20 06:56:20.022758');

```

#### You can also add multiple row at once
To insert multiple rows into a table using a single INSERT statement, you use the following syntax:

```
INSERT INTO table_name (column_list)
VALUES
(value_list_1),
(value_list_2),
(value_list_3),
......
(value_list_n);
```


```

INSERT INTO app_user(username, email, name, created_at) 
VALUES
('david', 'david@gmail.com', 'David Moore', '2021-09-20 06:56:20.022758'),
('jhon_doe', 'jhon.doe@gmail.com', 'Jhon Doe', '2021-09-20 06:56:20.022758'),
('stive008', 'stive.jhon@example.com', 'Jhon Stive', '2021-09-20 06:56:20.022758');

```

#### Insert data and return

To insert multiple rows and return the inserted rows, you add the RETURNING clause as follows:

```
INSERT INTO table_name (column_list)
VALUES
    (value_list_1),
    (value_list_2),
    ...
    (value_list_n)
RETURNING * | output_expression;
```

#### Example:

```

INSERT INTO app_user(username, email, name, created_at) 
VALUES
('david', 'david@gmail.com', 'David Moore', '2021-09-20 06:56:20.022758'),
('jhon_doe', 'jhon.doe@gmail.com', 'Jhon Doe', '2021-09-20 06:56:20.022758'),
('stive008', 'stive.jhon@example.com', 'Jhon Stive', '2021-09-20 06:56:20.022758');

RETURNING id, username;
```

#### Output:

```
 id | username  
----+-----------
  6 | david
----+-----------
  7 | jhon_doe
----+-----------
  8 | stive008
----+-----------
(3 rows)
```