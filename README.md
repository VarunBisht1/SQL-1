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

4- Select by Specific Librarian;
         
         SELECT * FROM books WHERE Issuedby = 'Librarian 1';

   ![image alt](https://github.com/VarunBisht1/SQL-1/blob/fe032c3f664b114843a2ae61479b032e2aea6e1e/output/Select%20by%20specific%20liberian.png)


5- Another table to use join query

    
     CREATE TABLE Librarian (
    Librarian_ID varchar(100),
    Librarian_Name VARCHAR(50)
    );
    INSERT INTO Librarian (Librarian_ID, Librarian_Name)
    VALUES
    ('Librarian 1', 'Rohan'),
    ('Librarian 2', 'Varun');
 ![image alt](https://github.com/VarunBisht1/SQL-1/blob/59d38fd0421ac5d3e21e0c25953689e9486f35b5/output/create%202.png)

6 - Inner Join :
        
    SELECT b.Book_Title, l.Librarian_Name,Book_Title
    FROM books b
    Inner JOIN Librarian l ON b.Issuedby = l.Librarian_ID;
   ![image alt](https://github.com/VarunBisht1/SQL-1/blob/59d38fd0421ac5d3e21e0c25953689e9486f35b5/output/Inner%20join.png)

7- Left Join  :

       SELECT b.Book_Title, l.Librarian_Name
       FROM books b
       Left JOIN Librarian l ON b.Issuedby = l.Librarian_ID;
   ![image alt](https://github.com/VarunBisht1/SQL-1/blob/59d38fd0421ac5d3e21e0c25953689e9486f35b5/output/left%20join.png)

 8- Right Join :
 
           SELECT b.Book_Title, l.Librarian_Name
           FROM books b
           right JOIN Librarian l ON b.Issuedby = l.Librarian_ID;
   ![image alt](https://github.com/VarunBisht1/SQL-1/blob/59d38fd0421ac5d3e21e0c25953689e9486f35b5/output/right.png)



 9-Display books issued by each librarian with their names:

           SELECT b.Book_Title, l.Librarian_Name
          FROM books b
          JOIN Librarian l ON b.Issuedby = l.Librarian_ID;

 ![image alt](
 
 10 -    Display the total number of books issued by each librarian:

             SELECT l.Librarian_Name, COUNT(*) AS Total_Books_Issued
            FROM books b
            JOIN Librarian l ON b.Issuedby = l.Librarian_ID
            GROUP BY l.Librarian_Name;
 ![image alt](https://github.com/VarunBisht1/SQL-1/blob/6c28b730f23aae351c93e9fbbfeeb8e551eaa47d/output/total.png)

  11-   Display the average publication year of books issued by each librarian:

              SELECT l.Librarian_Name, AVG(b.Publication_no) AS Avg_Publication_Year
              FROM books b
             JOIN Librarians l ON b.Issuedby = l.Librarian_ID
               GROUP BY l.Librarian_Name;

 ![image alt](https://github.com/VarunBisht1/SQL-1/blob/59d38fd0421ac5d3e21e0c25953689e9486f35b5/output/avg%20publica.png)

12 -  Display overdue books with the name of the issuing librarian:

      SELECT b.Book_Title, l.Librarian_Name ,b.over_due
     FROM books b
     JOIN Librarian l ON b.Issuedby = l.Librarian_ID
     WHERE b.Over_due = TRUE;
 ![image alt](https://github.com/VarunBisht1/SQL-1/blob/6c28b730f23aae351c93e9fbbfeeb8e551eaa47d/output/overdue.png)

    

         
          

        
      


   
                  
