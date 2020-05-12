# SQL

A cheat sheet for SQL.

## Simple commands

USE <name of database> - changes database to name of database

" * " - the star means all

CREATE TABLE <table name> - creates table

DROP TABLE <table name> - deletes table

SP_HELP <table name> -

ALTER TABLE <table name> ADD <column name> <data type> - adds a column

ALTER TABLE <table name> DROP COLUMN <column name>; - deletes column



## Intro to database

what is a datebase?
a collection of dat or a data repository


## Types of database

Flat-file database
- stroes everything in one table

Relational Database
- Gives you the ability to separte masses of data into numerous tables
- they are liked to each other thought the use of keys

Big Data
- used for Data Analytics and Business Intellingence
- Digitial Age and Internet of Things

Internet of Things are apps that can use other

## Relationship Types

One to One
- One row is link to one row on another table

One to Many
- One row is linked to many rows on another table

Many to Many
- Many rows connected to many other rows on another table


## Types of keys

PRIMARY KEY

- Is a uniquely identifier for each record in a table (normally first column)
- Most table should have a primary key
- In a table a column can have more than one primary key
- It can be automatically create by DBMS ​
- They must be unique​
- They must have an entry, must contain data​
- The value must never change ​
- Tables are linked by unique IDs ​
- A foreign key is a unique ID in another table

FOREIGN KEY

- Natural relationships exist between tables in most databases structures, foreign keys are used to create solid relationships​
- Foreign keys ensures that the row information in a table a corresponds to the correct row of the information in table b.​
- The constraint is used to prevent action that would destroy links between tables​
- It prevents  invalid information to be added in​
- There is no uniqueness constraint for a foreign key

COMPSITES KEY

-  When you have 2 primary keys in one table and both are need for uniquely identifies each row.

CANADIDATE KEY

- Canadidate keys are all unque keys that can be one PRIMARY KEY, the other ones are considered as Canadidate KEYS


## Structured Query Language

DML ( data manipulation language) - is a computer programming language used for adding (inserting), deleting, and modifying (updating) data in a database. A DML is often a sublanguage of a broader database language such as SQL, with the DML comprising some of the operators in the language.​

DDL ( data definition language) A data definition or data description language (DDL) is a syntax similar to a computer programming language for defining data structures, especially database schemas. DDL statements create and modify database objects such as tables, indexes, and users. Common DDL statements are CREATE, ALTER, and DROP​

DCL (data control language) A data control language (DCL) is a syntax similar to a computer programming language used to control access to data stored in a database (Authorization). In particular, it is a component of Structured Query Language (SQL).​

TCL ( transaction control language) Transaction Control Language commands are used to manage transactions in the database. These are used to manage the changes made by DML-statements. It also allows statements to be grouped together into logical transactions.


## Data Types

VARCHAR
varable lenght of charactors

CHAR
fixed lenght of charactors

INT
whole nubers

DATE ot TIME or DATETIME
stores date, time or both

DECIMAL or
