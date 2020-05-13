# List of commands with expalnation

- Do not add the square brackets, they are there as place holders.
- ; Is the end of commands

***
## Creates database
```SQL
CREATE DATABASE [database name];
```

***
## Changes database to name of database
```SQL
USE [name of database];
```

***
" * "
- The star means all, this can not be used by it self, but very useful in other commands

***
## Creates table
```SQL
CREATE TABLE [table name]

(

  [column name] [data type],

  PRIMARY KEY [column name],


[column name this table] [data type] FOREIGN KEY REFERENCES [table name](column name)

);
```
- creates table
- How to asign primary and foreign keys
- Be careful on format, you need the column name alredy in there
***
## Deletes table
```SQL
DROP TABLE [table name];
```
***

```SQL
SP_HELP [table name];
```
- Lets you check data types for table.
***
## Adds a Column
```SQL
ALTER TABLE [table name] ADD [column name] [data type];  
```
***
## Deletes column
```SQL
ALTER TABLE [table name] DROP COLUMN [column name];
```
***

***
## WHERE command and how to use

The 'WHERE' command fillters.
```SQL
SELECT *
FROM Employees
WHERE City = 'London';
```

***
## AND Opperator
```SQL
SELECT ProductName, UnitPrice
FROM Products
WHERE CategoryID=1 AND Discontinued = 0;
```

***
## TOP Opperator
```SQL
SELECT TOP 100 CompanyName, City
FROM Customers
WHERE Country='France';
```
***
## DISTINCT Opperator

Removes the duplicats

```SQL
SELECT DISTINCT Country
FROM Customers
WHERE ContactTitle = 'Owner';
```
***

## Wild Card Opperators
These normally work with LIKE

 % Subtitute for zero or more

 _ Subtitute for single charactor

[charlist] sets a a range for charactors to match ie LIKE [ABC]%

[^charlist] sets a a range for charactors that dont match LIKE [^ABC]%

Exmple of % Opperator

```SQL
SELECT p.ProductName
FROM Products p
WHERE p.ProductName LIKE 'E%';
```
In this case it look for any ProductName that starts form E

```SQL
SELECT p.ProductName
FROM Products p
WHERE p.ProductName LIKE '%E';
```
This is very similar but look for ends in E

Exapmles of charlist
```SQL
SELECT COUNT(o.OrderID) AS "Number of Orders"
FROM Orders o
WHERE o.EmployeeID LIKE '[5]';
```
This will look for Number of orders EmployeeID 5 made

```SQL
SELECT COUNT(o.OrderID) AS "Number of Orders"
FROM Orders o
WHERE o.EmployeeID LIKE '[57]';
```
This will look for Number of orders EmployeeID 5 and 7 made

This works for words as well, if it was '[BS]%'; example:

```SQL
SELECT c.CategoryName
FROM Categories c
WHERE c.CategoryName LIKE '[BS%]';
```
In this case it will display any CategoryName that starts with B or S

***
## IN opperator
```SQL
SELECT *
FROM Customers c
WHERE c.Region IN ('WA','SP');
```
You can look for specifice things

***
## Between
```SQL
SELECT *
FROM EmployeeTerritories
WHERE TerritoryID BETWEEN 06800 AND 09999;
```

***
## charlist

```SQL
SELECT COUNT(o.OrderID) AS "Number of Orders"
FROM Orders o
WHERE o.EmployeeID LIKE '[57]';
```

***

## Concatination
```SQL
SELECT e.FirstName +' '+ e.LastName AS "Employee Name"
FROM Employees e;
```
Just adds 2 string together, in this case adds first and last name and the AS opperator is used for alias
***
## Using ORDER BY and DESC, ORDER BY sorts the able and DESC spicifies the desending order
```SQL
SELECT UnitPrice, Quantity, Discount, UnitPrice * Quantity *(1-Discount) AS "Net Total"
FROM [Order Details]
ORDER BY "Net Total" Desc
```
- If you
***
# Join Queries
INNER JOIN: returns records that have matching value in both tables
```SQL
SELECT column_names FROM table1 INNER JOIN table2 ON table1.column_name=table2.column_name;

SELECT table1.column_name1, table2.column_name2, table3.column_name3 FROM ((table1 INNER JOIN table2 ON relationship) INNER JOIN table3 ON relationship);
```

LEFT (OUTER) JOIN: returns all records from the left table (table1), and the matched records from the right table (table2)
```SQL
SELECT column_names FROM table1 LEFT JOIN table2 ON table1.column_name=table2.column_name;
```
RIGHT (OUTER) JOIN: returns all records from the right table (table2), and the matched records from the left table (table1)
```SQL
SELECT column_names FROM table1 RIGHT JOIN table2 ON table1.column_name=table2.column_name;
```
FULL (OUTER) JOIN: returns all records when there is a match in either left or right table
```SQL
SELECT column_names FROM table1 FULL OUTER JOIN table2 ON table1.column_name=table2.column_name;
```
Self JOIN: a regular join, but the table is joined with itself
```SQL
SELECT column_names FROM table1 T1, table1 T2 WHERE condition;
```
