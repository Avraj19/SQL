# SQL Queries

## Linking two tables
How to link 2 or more table with PRIMARY and FOREIGN KEYS.

### Step 1:
Make one table and asign a primary key to it.

```SQL
CREATE TABLE staff_details
(
    staff_id INT IDENTITY(1,1),
    staff_first_name VARCHAR(10),
    staff_middle_name VARCHAR(10),
    staff_last_name VARCHAR(10),
    PRIMARY KEY (staff_id)
);
```
### Step 2
Create a second table, asign a foreign key to it.

```SQL
CREATE TABLE work_hours
(
    dates VARCHAR(10),
    hours_working INT,
    start_time TIME,
    end_time TIME,
    PRIMARY KEY (dates),
    staff_id INT IDENTITY(1,1) FOREIGN KEY REFERENCES staff_details(staff_id)
);
```
***

## Different ways of inserting data in table

### First and most Used

The first way is when enter column name and under VALUES fill info.
```SQL
INSERT INTO staff_details
(
    staff_first_name, staff_last_name
)
VALUES
(
    'Avraj', 'Singh'
);
```

### Second only useful if you know the table


```SQL
INSERT INTO staff_details
VALUES
(
    'Avraj', 'Singh'
);
```

***
## NULL

NULL is undefinded value, do not mistake for nothing



***

## Updating the table info or table struture

This changes on row on a table.

```SQL
UPDATE staff_details
SET staff_middle_name='Batch'
WHERE staff_id=2;
```

- The WHERE command let you specifiy which row you want to effect.

***
## Normal Form

### 1st Normal Form
- Make everythng atomic
- There should be no repeatiing groups

There should only be one bit of data in one cell. If there is more than one bit of information in a cell, try to splite it into different tables.

In this case the table will use a compsite key (in most cases).

### 2nd Normal Form
- Must follow 1st Normal Form
- All non-key attributes are fully functional dependent on the primary key

### 3rd Normal forma



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
WHERE c.CategoryName LIKE '[BS%]'
```
In this case it will display any CategoryName that starts with B or S

***
## IN opperator
```SQL
SELECT *
FROM Customers c
WHERE c.Region IN ('WA','SP')
```
You can look for specifice things

***
## Between
```SQL
SELECT *
FROM EmployeeTerritories
WHERE TerritoryID BETWEEN 06800 AND 09999
```

***
## charlist

```SQL
SELECT COUNT(o.OrderID) AS "Number of Orders"
FROM Orders o
WHERE o.EmployeeID LIKE '[57]'
```

***

## Concatination
```SQL
SELECT e.FirstName +' '+ e.LastName AS "Employee Name"
FROM Employees e
```
Just adds 2 string together, in this case adds first and last name and the AS opperator is used for alias
