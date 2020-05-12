# List of commands with expalnation

- Do not add the square brackets, they are there as place holders.
- ; Is the end of commands

***
CREATE DATABASE [database name];
- creates database
***

USE [name of database];
- changes database to name of database
***

" * "
- The star means all, this can not be used by it self, but very useful in other commands
***

CREATE TABLE [table name]

(

  [column name] data type,

  PRIMARY KEY [column name],


[other table name] [data type] FOREIGN KEY REFERENCES [table name] (column name)

);
- creates table
- How to asign primary and foreign keys
***

DROP TABLE [table name]
- Deletes table
***

SP_HELP [table name];
- g
***

ALTER TABLE [table name] ADD [column name] [data type];  
- Adds a column
***
ALTER TABLE <table name> DROP COLUMN <column name>; - deletes column
