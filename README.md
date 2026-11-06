AUTHOR : Lemuel Waye Otoo-Biney

1.Database Purpose
------------------
* The Library database is created to store the data of books stored, customer's name
  ,last name of the people that borrow the books or have a library membership which keeps
  track of all the accurate information relating to the library and makes it easy to search,
  arrange for available books.


2.Table Separation
------------------
These Subject Tables avoid data repition or redundancy for the database by storing details 
in different tables.

* Books table 
-------------
- Stores information on the Books that are in the library such as the serial number.

* Member table
--------------
- Stores the details of the people who have a membership such as member id.

* Borrowings table
------------------
- Stores the details of people who have borrowed a book such as customer name.

* Authors table
----------------
- Stores the details of the authors of each book in the library such as author name.


3.Fields & Primary Keys
------------------------

Members table
-------------
- members_id = serial, Primary Key.
- first_name = varchar, first name of the member.
- last_name = varchar, last name of the member.
- date_of_membership = date of membership.
- email_address = varchar, is the email of the member.
- phone_number = numeric, is the phone number of the member.

------------------------------------------------------------------
QUERIES AFTER INSERTING INTO book AND ORDER Tables
---------------------------------------------------------------------


library_db=# SELECT * FROM books;
 book_id |                    title                    | published_year | author_id
---------+---------------------------------------------+----------------+-----------
      33 | African Artificial Intelligence             |           2024 |       121
      87 | Figure Drawing: Design and invention        |           2024 |       546
      99 | Figure Drawing for Alls its Worth           |           2023 |       875
     142 | Mastering Sovereign Artificial Intelligence |           2025 |       121
(4 rows)


library_db=# SELECT * FROM authors;
 author_id |   author_name
-----------+-----------------
       121 | Mark Nasila
       546 | Micheal Hamptom
       875 | Andrew Loomis
(3 rows)


library_db=# SELECT b.title, a.author_name, b.book_id FROM books b JOIN authors a ON b.author_id = a.author_id;
                    title                    |   author_name   | book_id
---------------------------------------------+-----------------+---------
 African Artificial Intelligence             | Mark Nasila     |      33
 Figure Drawing: Design and invention        | Micheal Hamptom |      87
 Figure Drawing for Alls its Worth           | Andrew Loomis   |      99
 Mastering Sovereign Artificial Intelligence | Mark Nasila     |     142
(4 rows)



