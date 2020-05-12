# List of commands with expalnation

- Do not add the square brackets, they are there as place holders.
- ; Is the end of commands

***
```SQL
CREATE DATABASE [database name];
```
- creates database

***
```SQL
USE [name of database];
```
- changes database to name of database

***
" * "
- The star means all, this can not be used by it self, but very useful in other commands

***
```SQL
CREATE TABLE [table name]

(

  [column name] [data type],

  PRIMARY KEY [column name],


[column name this table] [data type] FOREIGN KEY REFERENCES [table name](column name)

);
```
- codereates table
- How to asign primary and foreign keys
- Be careful on format, you need the column name alredy in there
***

```SQL
DROP TABLE [table name];
```
- Deletes table
***

```SQL
SP_HELP [table name];
```
- Lets you check data types for table.
***

```SQL
ALTER TABLE [table name] ADD [column name] [data type];  
```
- Adds a column
***

```SQL
ALTER TABLE [table name] DROP COLUMN [column name];
```
- Deletes column
