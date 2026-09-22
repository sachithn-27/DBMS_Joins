
CREATE TABLE Customers (
    CustomerID INT PRIMARY KEY,
    CustomerName VARCHAR(50),
    City VARCHAR(50)
);

CREATE TABLE Orders (
    OrderID INT PRIMARY KEY,
    CustomerID INT,
    Product VARCHAR(50),
    Price DECIMAL(10, 2)
);

INSERT INTO Customers (CustomerID, CustomerName, City) VALUES
(1, 'Alice', 'New York'),
(2, 'Bob', 'London'),
(3, 'Charlie', 'Paris'),
(4, 'David', 'Tokyo');

INSERT INTO Orders (OrderID, CustomerID, Product, Price) VALUES
(101, 1, 'Laptop', 1200.00),
(102, 2, 'Phone', 800.00),
(103, 1, 'Mouse', 20.00),
(104, 99, 'Keyboard', 50.00);

SELECT 'INNER JOIN' AS JoinType, C.CustomerName, O.Product, O.Price
FROM Customers C
INNER JOIN Orders O ON C.CustomerID = O.CustomerID;

SELECT 'LEFT JOIN' AS JoinType, C.CustomerName, O.Product, O.Price
FROM Customers C
LEFT JOIN Orders O ON C.CustomerID = O.CustomerID;

SELECT 'RIGHT JOIN' AS JoinType, C.CustomerName, O.Product, O.Price
FROM Customers C
RIGHT JOIN Orders O ON C.CustomerID = O.CustomerID;
