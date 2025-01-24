# CODTECH-A-TASK-1

**NAME** : ARYA P P

**COMPANY** : CODTECH IT SOLUTIONS

**INTERN ID** : CT08FSQ

**DOMAIN NAME** : SQL

**BATCH DURATION** : December 30th 2024 to January 30th 2025

**MENTOR NAME** : NEELA SANTHOSH KUMAR

OVERVIEW OF THE PROJECT:

PROJECT:LIBRARY MANAGEMENT SYSTEM

#INTRODUCTION

This project focuses on creating a simple Library Management System using a relational database. The system manages Books, Members, and Transactions. It allows for efficient management of books, member records, and book transactions (borrow and return). This system also ensures that the available copies of each book are updated in real time based on borrowing and returning actions, using triggers to automate these updates.

#OBJECTIVE

The objective of this project is to:
•	Implement a relational database schema to manage books, members, and transactions.
•	Automate the update of available copies of books when borrowed and returned.
•	Provide SQL queries for common library operations like adding books, updating book details, deleting books, and handling transactions.

#KEY FEATURES

o	Books Table:
Stores information about books like BookID, Title, Author, Genre, PublishedYear, TotalCopies, and AvailableCopies.

o	Members Table:
Stores details of library members including MemberID, Name, Email, Phone number, and JoinDate.

o	Transactions Table:
Tracks borrowing and returning of books, with details such as TransactionID, MemberID, BookID, BorrowDate, and ReturnDate.

o	Triggers:
Decrease_AvailableCopies: Automatically decreases the available copies when a new book is borrowed (when ReturnDate is NULL).
Increase_AvailableCopies: Automatically increases the available copies when a book is returned (when ReturnDate is not NULL).

#DATABASE SCHEMA

o	Books Table:
create table Books(
  BookID integer primary key,
  Title varchar(100) not null,
  Author varchar(100) not null,
  Genre varchar(50),
  PublishedYear integer,
  TotalCopies integer not null,
  AvailableCopies integer not null);

o	Members Table:
create table Members(
  MemberID integer primary key,
  Name varchar(100) not null,
  Email varchar(100) unique not null,
  Phone number unique not null,
  JoinDate date default current_date);

o	Transactions Table:
create table Transactions(
  TransactionID integer primary key,
  MemberID integer not null,
  BookID integer not null,
  BorrowDate date default current_date,
  ReturnDate date,
  foreign key (MemberID) references Members (MemberID),
  foreign key (BookID) references Books (BookID));

#LIMITATIONS

o	Basic Functionality:
The system only manages book borrowing and returning. It does not include features like reservations, overdue fees, or book suggestions.
Error Handling:
The system does not implement comprehensive error handling for cases such as trying to borrow a book with no available copies.

o	Scalability:
The system is designed for small to medium-sized libraries and might need optimizations for large-scale operations.

#FUTURE IMPROVEMENTS

o	Overdue Book Handling:
Implement a feature to track overdue books and impose fines.

o	Book Reservation:
Add functionality to allow members to reserve books that are currently unavailable.

o	Enhanced User Interface:
Develop a web or mobile interface for easier interaction with the library system.

o	Reporting:
Add reporting capabilities, such as the most borrowed books, active members, etc.

#SYSTEM STUDY

o	System Overview: 
This Library Management System (LMS) aims to streamline the management of books, members, and transactions in a library environment. The system uses a relational database to store data related to books, library members, and the borrowing/returning of books. SQL queries and triggers are used to handle various operations like adding, updating, deleting books, and automating the process of managing available copies when books are borrowed or returned.

o	System Objectives:
•	To provide an efficient way of managing library data.
•	To automate book borrowing and returning operations using triggers.
•	To ensure the integrity and consistency of available book copies using database triggers.

o	System Requirements:
Hardware Requirements:
•	A computer system capable of running SQL-based database management systems like Oracle or MySQL.
•	Sufficient storage for the database and backup files.
Software Requirements:
•	Database Management System (DBMS) such as Oracle or MySQL.
•	SQL client tools (e.g., SQL*Plus, MySQL Workbench).

#SYSTEM DESIGN

o	Database Design: 
The database is designed with three main tables: Books, Members, and Transactions.

o	Books Table:
Holds the details of books such as book ID, title, author, genre, and available copies.
The AvailableCopies field is automatically updated through triggers when a book is borrowed or returned.

o	Members Table:
Stores information about library members, including member ID, name, email, phone number, and the join date.

o	Transactions Table:
Tracks the borrowing and returning of books.
It references both the Members and Books tables to establish relationships.

o	Data Flow:
A member borrows a book, creating a record in the Transactions table.
The Decrease_AvailableCopies trigger is fired, updating the AvailableCopies of the book in the Books table.
When a book is returned, the Increase_AvailableCopies trigger is fired, incrementing the AvailableCopies field.

#MODULES

o	Books Module:
Create: Allows the addition of new books to the library.
Update: Enables updates to existing books (e.g., change the number of total and available copies).
Delete: Deletes a book from the library when it is no longer needed.

o	Members Module:
Create: Adds new members to the library system.
Update: Modifies member details (e.g., name, phone number, or email).
Delete: Removes a member from the system when they are no longer a part of the library.

o	Transactions Module:
Borrow Book: A member borrows a book, which is recorded in the Transactions table and decreases the AvailableCopies.
Return Book: A member returns a book, updating the Transactions table and increasing the AvailableCopies.

o	Triggers Module:
Decrease_AvailableCopies: Decreases the available copies of a book when a transaction is inserted (book borrowed).
Increase_AvailableCopies: Increases the available copies when a transaction is updated (book returned).

#CONCLUSION

The Library Management System developed here is a simple yet effective solution for managing a small to medium-sized library. It leverages the power of relational databases and SQL triggers to automate the update of book availability as transactions (borrow and return) occur.
o	Key Takeaways:
•	The system ensures data consistency and reduces manual updates by automating the process of tracking available copies of books.
•	The modular design allows for easy future enhancements, such as implementing overdue book tracking or adding book reservations.
•	The design is scalable for small to medium-sized libraries, and with future improvements, it could support more complex features for larger libraries.

#OUTPUT

![Image](https://github.com/user-attachments/assets/f5f0fe1c-5cb6-4219-877b-be834067a5d8)

![Image](https://github.com/user-attachments/assets/2542d60c-5598-4e26-ada4-2fe2b9339a72)

![Image](https://github.com/user-attachments/assets/16f17873-f572-4c2d-91c5-df37a62f9b1e)

![Image](https://github.com/user-attachments/assets/586c68eb-f7eb-48fa-8a9f-cbf2975130c3)

![Image](https://github.com/user-attachments/assets/de23e7af-e939-48e4-a4e0-6788f4c5f8ac)

![Image](https://github.com/user-attachments/assets/d60cd29d-3584-44e8-9b9b-0676eee5d5eb)

![Image](https://github.com/user-attachments/assets/c2ae89a2-2e10-462b-bd9e-2f94d58cdee7)

