CREATE TABLE Employees (
    EmpID INTEGER PRIMARY KEY,
    FirstName TEXT,
    LastName TEXT,
    Age INTEGER,
    Department TEXT,
    Salary REAL,
    Email TEXT DEFAULT NULL
);
INSERT INTO Employees (EmpID, FirstName, LastName, Age, Department, Salary, Email)
VALUES (1, 'John', 'Doe', 30, 'HR', 50000.00, 'john.doe@example.com');
INSERT INTO Employees (EmpID, FirstName, LastName, Age, Department, Salary, Email)
VALUES (2, 'Jane', 'Smith', NULL, 'Finance', 60000.00, NULL);
INSERT INTO Employees (EmpID, FirstName, Department, Salary)
VALUES (3, 'Raj', 'IT', 55000.00);
UPDATE Employees
SET Age = 28
WHERE EmpID = 2;
UPDATE Employees
SET Salary = Salary + 5000
WHERE Department = 'IT';
DELETE FROM Employees
WHERE EmpID = 3;
BEGIN TRANSACTION;
DELETE FROM Employees WHERE EmpID = 2;
ROLLBACK;
INSERT INTO Employees (EmpID, FirstName, LastName, Age, Department, Salary, Email)
SELECT 4, FirstName, LastName, Age, Department, Salary, Email
FROM Employees
WHERE EmpID = 1;
SELECT * FROM Employees;
