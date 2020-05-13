# SQL wed

Objectives:
- Continue with data-base querying
- Join sub queries
- Group by having in detail
- Union and union all
- String methods
- Sorting
- Date functions
- Case statements
- Aggregate functions
- Review of on delete cascade

***
## Gross Total

```SQL
SELECT UnitPrice*Quantity AS "Gross Total"
FROM [Order Details]
```
***
## Net Total
```SQL
SELECT UnitPrice, Quantity, Discount, UnitPrice * Quantity *(1-Discount) AS "Net Total"
FROM [Order Details]
```
***
## Using ORDER BY and DESC, ORDER BY sorts the able and DESC spicifies the desending order
```SQL
SELECT UnitPrice, Quantity, Discount, UnitPrice * Quantity *(1-Discount) AS "Net Total"
FROM [Order Details]
ORDER BY "Net Total" Desc
```
***
## CHARINDEX
A CHARINDEX is a way of filltering stings

```SQL
SELECT p.ProductName
FROM Products p
WHERE CHARINDEX('''',p.ProductName) > 0
```
- In this case we are filltering for ProductName with ' in the name some where.
- In this case
***

## GROUP BY

```SQL
SELECT SUM(UnitsOnOrder) AS "Total On Order",
AVG(UnitsOnOrder) AS "Avg On Order",
MIN(UnitsOnOrder) AS "Min On Order",
MAX(UnitsOnOrder) AS "Max On Order"
FROM Products p
```
- Without GROUP BY, the calcuation will all be compressed in one row

```SQL
SELECT p.SupplierID,
SUM(p.UnitsOnOrder) AS "Total On Order",
AVG(UnitsOnOrder) AS "Avg On Order",
MAX(UnitsOnOrder) AS "Max On Order"
FROM Products p
GROUP BY p.SupplierID
```
- By adding GROUP BY, you get a much clear pic of Orders

***
## INNER JOINS
``` sql
SELECT AVG(p.UnitsOnOrder) AS "Avg Units on Order", CompanyName
FROM Products p
INNER JOIN Suppliers s
ON p.SupplierID = S.SupplierID
GROUP BY p.SupplierID
````
- You can connect with multiplue tables as long as there is a primary and forgien key link.
```SQL
SELECT o.OrderID, o.OrderDate, o.Freight,
e.FirstName +' '+ e.LastName AS 'Employee Name', c.CompanyName
FROM Orders o
INNER JOIN Employees e ON o.EmployeeID = e.EmployeeID
INNER JOIN Customers c ON o.CustomerID = o.CustomerID
```
