USE LibraryDB;
INSERT INTO Authors (Name, Country) VALUES 
('J.K. Rowling', 'UK'),
('George Orwell', 'UK'),
('Chetan Bhagat', 'India');
INSERT INTO Books (Title, Genre, PublishedYear, AuthorID) VALUES 
('Harry Potter', 'Fantasy', 2001, 1),
('1984', 'Dystopian', 1949, 2),
('Five Point Someone', 'Fiction', 2004, 3);
INSERT INTO Members (Name, Email, Phone, MembershipDate) VALUES 
('Alice Sharma', 'alice@gmail.com', '9876543210', '2023-01-10'),
('Bob Verma', 'bob@yahoo.com', '9123456780', '2023-03-20');
INSERT INTO Staff (Name, Role, Email) VALUES 
('Anjali Mehta', 'Librarian', 'anjali@library.com'),
('Ravi Kumar', 'Assistant', 'ravi@library.com');
INSERT INTO Borrow (BookID, MemberID, BorrowDate, ReturnDate) VALUES 
(1, 1, '2024-01-15', '2024-02-01'),
(2, 2, '2024-02-10', NULL);
UPDATE Members
SET Phone = '9999999999'
WHERE Name = 'Alice Sharma';
UPDATE Staff
SET Role = 'Senior Librarian'
WHERE Name = 'Anjali Mehta';
DELETE FROM Books
WHERE Title = '1984';
BEGIN;
DELETE FROM Members WHERE Name = 'Bob Verma';
ROLLBACK;
SELECT * FROM Members;
