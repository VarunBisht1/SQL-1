Creating a Library Database and Performing SQL Queries

 Database Creation and Table Structure

       CREATE DATABASE Library
1- To Create Database and Table

    Create Database Library_;
    use Library_;
    CREATE TABLE books (
       ISBN INT PRIMARY KEY,
        Publisher_name VARCHAR(100),
        Publication_no INT,
        Book_Title VARCHAR(255),
        Book_library_no INT,
        Issuedate DATE,
        Issuedby VARCHAR(1000),
        Bookreturndate DATE,
        Over_due BOOLEAN
    );

2- Insert  Queries-

           INSERT INTO books (ISBN, Publisher_name, Publication_no, Book_Title, Book_library_no, Issuedate, Issuedby, Bookreturndate, Over_due)
           VALUES
                (123457890, 'Publisher A', 123, 'Book Title 1', 101, '2023-11-07', 'Librarian 1', '2023-11-21', FALSE),
                (987654210, 'Publisher B', 456, 'Book Title 2', 102, '2023-11-10', 'Librarian 2', '2023-11-25', FALSE),
                (1112223334, 'Publisher C', 789, 'Book Title 3', 103, '2023-11-12', 'Librarian 1', NULL, TRUE),
                (444556667, 'Publisher D', 101, 'Book Title 4', 104, '2023-11-15', 'Librarian 2', '2023-11-28', FALSE),
                (777888990, 'Publisher E', 234, 'Book Title 5', 105, '2023-11-17', 'Librarian 1', NULL, TRUE),
                (222333445, 'Publisher F', 567, 'Book Title 6', 106, '2023-11-19', 'Librarian 2', '2023-12-02', FALSE),
                (555666778, 'Publisher G', 890, 'Book Title 7', 107, '2023-11-21', 'Librarian 1', NULL, TRUE);

![image alt](https://github.com/VarunBisht1/SQL-1/blob/690fbce8fb54106d823e7bbffa204d901f70ef78/output/Create%20and%20insert.png)

3- Select Query 

       Select * from books;

4-
                  
