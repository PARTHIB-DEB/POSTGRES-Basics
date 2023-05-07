
# Basic PostGresql Commands :elephant: :elephant: :elephant:

Its a simple cheatsheet of POSTGRE-SQL database commands.


## Commands

To see all SQL databases using POSTGRES technology

```bash
  \l
```

To Create a new database (default database name is 'postgres')

```bash
  CREATE DATABASE db_name ;
```
To Delete a new database 

```bash
  DROP DATABASE db_name ;
```
How to move from one database to another

```bash
  \c db_name 
```
How to clear screen in PSQL SHELL

```bash
  \! cls
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
  column_name DATATYPE CONSTRAINTS,
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
  DROP TABLE table_name ;
```
To fetch a specific column/s details from a table(different values of a specific column/s)

```bash
  SELECT column_1,column_2 FROM table_name ;
```

Arranging the whole table on  specific column/s (by ascending/descending order)

```bash
  SELECT * FROM table_name ORDER BY col_1,col_2;
```
```bash
  SELECT * FROM table_name ORDER BY col_name ASC ;
```
```bash
  SELECT * FROM table_name ORDER BY col_name DESC ;
```

To show distinct values of a specific column

```bash
  SELECT DISTINCT col_name FROM table_name ORDER BY col_name ;
```

Generate a SUB-TABLE from a main table on the basis of a specific column/s value

```bash
  SELECT * FROM table_name WHERE col_name1="value1" AND col_name2="value2" ;
```
```bash
  SELECT * FROM table_name WHERE col_name IN ('value1','value2',.......) ;
```

In a more mature way...

```bash
  SELECT * FROM table_name WHERE col_name1="value1" AND (col_name2="value2" OR col_name3="value3) ;
```

Limiting datas of a table

***From 1 to limit***
```bash
  SELECT * FROM table_name LIMIT number ;
```

**OR**

```bash
  SELECT * FROM table_name FETCH FIRST num ROW ONLY ;
```
***From offset to limit***

```bash
  SELECT * FROM table_name OFFSET number1 LIMIT number2 ;
```

**OR**

```bash
  SELECT * FROM table_name OFFSET num1 FETCH FIRST num2 ROW ONLY ;
```
***REMEMBER :*** We can break a long commnads in some pieces but we must not put any *;* after each line until the last line comes!!

Using the LIKE method to fetch a specific subtable

```bash
  SELECT * FROM table_name WHERE col_name1 LIKE '%matchingphrases';
```
Fetching a subtable by grouping a specific column datas

```bash
  SELECT col_name FROM table_name GROUP BY col_name ;
```
Showing a single outcome of values in a specific column from a table (same for AVG, ROUND , SUM)

```bash
  SELECT MAX(col_name) FROM table_name ;
```

```bash
  SELECT MIN(col_name) FROM table_name ;
```
***Remember :*** We can nest this functions also

a little more mature table command using ORDER BY and these functions(fn -> math functions)

```bash
  SELECT col_x,col_y,fn(col_z).... FROM table_name ORDER BY col_x,col_y ;
```
Performing some arithmatic operations

```bash
  SELECT X ARITH(Replace this with operator) Y ;
```
To manipulate column values

```bash
  SELECT col_1,col_2....,fn(col_n) FROM table_name ;
```

To show the table by replacing some ***blank*** column value

```bash
  SELECT COALESCE(col_name,'default_statement/value') FROM table_name ;
```

**Primary Key:** Its a way to distinguish two records of having some or totally same datas. However we can create an object of same primary key (may or maynot same data of both records) ,let

```bash
  CREATE TABLE(
  id INT NOT NULL PRIMARY KEY,);
```
Now to make another record of same *Pkey*

```bash
  ALTER TABLE table_name DROP CONSTRAINT tabname_pkey ;
```

To search some datas from a table based on a value

```bash
  SELECT * FROM table_name WHERE col_name=value(either 'string' or numeric according to datatype)
```
**For DELETION**, either we can **delete database (Not preferred :X:)** , **Delete (drop) a table**, OR,
**Delete a specific record by identifying its id (because in general , id/Pkey is the unique)

```bash
  DELETE FROM table_name WHERE col_name=value(number or 'string') ;
```
**For Addition of a COLUMN or CONSTRAINTS** , we use **ALTER TABLE** command
https://www.postgresql.org/docs/current/sql-altertable.html

```bash
  ALTER TABLE table_name ADD COLUMN col_name constraints
```
```bash
  ALTER TABLE table_name ADD CONSTRAINT(col_name)
```
**Foreign-key :**A foreignkey field of a particular table is the *Primary-Key* of another table ; That's how , we can connect more tables by building O-O,O-M,M-M relations
and justifies the name of *RELATIONAL DATABASE*
To apply a foreignkey in practice , command is:

```bash
  CREATE TABLE tab_01_name{
  .
  .
  .
  .
  parent_id XXXYYYYYYYZZZ REFERENCES tab_02_name(target_id)
  }
```
*For O-O relations* - one elements of tab_02_name(target_id) will be assigned to only one element of tab_01_name(parent_id) , so

```bash
  UNIQUE(parent_id)
```



***TO BE CONTINUED . . . .*** :elephant: :elephant: :elephant:
