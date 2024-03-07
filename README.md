# Data-Warehouse-Implementation-and-Optimization--- Create tables for your data warehouse schema
CREATE TABLE Dim_Customer (
    CustomerID INT PRIMARY KEY,
    Name VARCHAR(255),
    Email VARCHAR(255),
    -- Other customer attributes
);

CREATE TABLE Dim_Product (
    ProductID INT PRIMARY KEY,
    Name VARCHAR(255),
    Category VARCHAR(50),
    -- Other product attributes
);

CREATE TABLE Fact_Sales (
    SalesID INT PRIMARY KEY,
    CustomerID INT,
    ProductID INT,
    SaleDate DATE,
    Quantity INT,
    Amount DECIMAL(10, 2),
    FOREIGN KEY (CustomerID) REFERENCES Dim_Customer(CustomerID),
    FOREIGN KEY (ProductID) REFERENCES Dim_Product(ProductID)
);
