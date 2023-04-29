
# Basic PostGresql Commands :elephant: :elephant: :elephant:

Its a simple cheatsheet of POSTGRESQL database commands.


## Commands

To Create a new database (default database name is 'postgres')

```bash
  CREATE DATABASE db_name;
```
To Delete a new database 

```bash
  DROP DATABASE db_name;
```
How to Create a table, follow the commands part by part

STEP-1:
```bash
  CREATE TABLE table_name(
```
STEP-2: [Provide necessary column names with their datatypes]

https://www.postgresql.org/docs/current/datatype.html

```bash
  column_name DATATYPE(numeric limit),
```
STEP-3: [Finishing the table]
```bash
  end_colname DATATYPE(num_limit));
```
Remember The CAPS words must be in CAPS !!

To check the tables in a database
```bash
  \d
```
To check details inside a specific table

***Way-1 :***
```bash
  \d table_name
```
***Way-2 :***
```bash
  SELECT * FROM table_name ;
```

To create more mature Table , we have to add **constraints** inside the command of each column,
such constraints like **primary key**,**not null** etc.

https://www.postgresql.org/docs/current/ddl-constraints.html
```bash
(column_name DATATYPE CONSTRAINTS,
```
To insert a new record / row / object in table

https://www.postgresql.org/docs/current/sql-insert.html

```bash
  INSERT INTO table_name(
  column_1,
  column_2,
  .
  .
  .
  )
  VALUES(value_1,value_2.....)
```
**Remember :** In case if any column has **NOT NULL** constraint , then you have to add that column value.

How to delete a table

```bash
  DROP TABLE table_name;
```
To fetch a specific column/s details from a table(different values of a specific column/s)

```bash
  SELECT column_1,column_2 FROM table_name ;
```

Arranging a specific column by ascending/descending order

```bash
  SELECT * FROM table_name ORDER BY col_name ASC ;
```
```bash
  SELECT * FROM table_name ORDER BY col_name DESC ;
```
