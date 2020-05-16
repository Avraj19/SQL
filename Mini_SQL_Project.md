# Mini SQL project

This md file contanes awnser for SQL Mini project.

```SQL
--1.1
SELECT c.CustomerID,c.CompanyName, c.Country, c.Address,City, c.PostalCode
FROM Customers c
WHERE c.City = 'London' OR c.City = 'Paris';

--1.2
SELECT p.QuantityPerUnit AS "Products stroed in bottles"
FROM Products p
WHERE p.QuantityPerUnit Like '%bottles%';

--1.3
SELECT s.CompanyName AS "Company Name", s.Country,
p.QuantityPerUnit AS "Products stroed in bottles"
FROM Products p
INNER JOIN Suppliers s ON p.SupplierID = s.SupplierID
WHERE p.QuantityPerUnit Like '%bottles%';

--1.4
SELECT c.CategoryID, c.CategoryName, COUNT(p.ProductID) AS "Number of Products"
FROM Categories c LEFT OUTER JOIN Products p
ON c.CategoryID = p.CategoryID
GROUP BY c.CategoryID, c.CategoryName
ORDER BY COUNT(P.ProductID) DESC;

--1.5
SELECT e.TitleOfCourtesy +' '+ e.FirstName +' '+ e.LastName AS "Employee Name", e.City
FROM Employees e
WHERE Country IN('UK');

--1.6
SELECT (RegionDescription) AS 'Region',
ROUND(SUM(UnitPrice * Quantity * (1-Discount)),2) AS 'Total Sales Per Region'
FROM Region r
INNER JOIN Territories t
ON  r.RegionID = t.RegionID
INNER JOIN EmployeeTerritories et
ON t.TerritoryID = et.TerritoryID
INNER JOIN Orders o
ON  o.EmployeeID = et.EmployeeID
INNER JOIN [Order Details]
ON  o.OrderID = [Order Details].OrderID
GROUP BY RegionDescription  
HAVING SUM(UnitPrice * Quantity * (1-Discount)) > 100000;


--1.7
SELECT COUNT(o.OrderID) AS "Freight Count"
FROM Orders o
WHERE  o.Freight < 100 AND o.ShipCountry = 'USA' OR o.ShipCountry = 'UK';

--1.8
SELECT TOP 1 o.OrderID, SUM(o.UnitPrice * o.Quantity * (1- o.Discount)) AS "Highest Discount Applied"
FROM [Order Details] o
GROUP BY o.OrderID
ORDER BY 'Highest Discount Applied' DESC;

--2.1
CREATE TABLE SpartaTable
(
    StudentID INT IDENTITY(1,1) PRIMARY KEY, Title CHAR(5), FirstName VARCHAR(15), LastName VARCHAR(15), University VARCHAR(50),
    Course VARCHAR(60), Marks CHAR(3)
);

--2.2
INSERT INTO SpartaTable
VALUES
(
    'Mr.', 'Avraj', 'Singh', 'University of East London', 'Mechanical Engineering', '2:1'
);

--3.1
SELECT emp.FirstName, emp.LastName, sup.LastName+' '+ sup.FirstName AS 'Supervisor'
FROM Employees  emp
INNER JOIN Employees  sup
ON emp.ReportsTo = sup.EmployeeID



--3.2
SELECT Suppliers. SupplierID, Products. UnitPrice * Quantity *(1-Discount) AS 'Total Sales', CompanyName
FROM [Order Details]
INNER JOIN Products
ON [Order Details].ProductID = Products.ProductID
INNER JOIN Suppliers
ON Products.SupplierID = Suppliers.SupplierID
WHERE Products.UnitPrice * Quantity > 10000;



--3.3
SELECT ShippedDate, CustomerID, COUNT(OrderID) AS 'Orders'
FROM Orders
WHERE OrderDate BETWEEN '1996/01/01' AND '1999/12/31'
GROUP BY CustomerID, ShippedDate
ORDER BY 'Orders' DESC

--3.4
SELECT FORMAT(ShippedDate, 'MMM/yy') AS 'Month/Year',
AVG(DATEDIFF(d, OrderDate, ShippedDate)) AS 'Avrage Spipping Time'
FROM Orders
WHERE ShippedDate IS NOT NULL
GROUP BY FORMAT(ShippedDate, 'MMM/yy')
ORDER BY 'Avrage Spipping Time' DESC;
