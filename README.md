<a name="readme-top"></a>

# Library Management System 
(problem 1 for the Siemens internship challange)

## Scenario:
  You are tasked with designing a library management system for a university. The system should allow
librarians to manage books, patrons, and borrowing activities efficiently.

## Requirements:
###  Book Management:
* Books have attributes like Title, Author, ISBN, and Quantity.
* Patrons can borrow multiple books.
* A book can be borrowed by multiple patrons.
###  Patron Management:
* Patrons have attributes like Name, ID, and Contact Information.
* Each patron can borrow a limited number of books at a time.
* Patrons can have fines if books are returned late.
###  Borrowing System:
* Books can be borrowed for a specific duration.
* Calculate fines for late returns based on a predefined fine rate.

## Tasks:
###  Class Diagram:
  Create a class diagram showing the relationship between Book, Patron, and Borrowing.
Include relevant attributes and relationships between classes.
###  Database Diagram:
  Design a database schema representing the entities Book, Patron, and Borrowing.
Define the relationships between tables and attributes.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

# Problem Solving

In this section, I'll detail the problem-solving process for designing the Library Management System. I'll cover the key tasks outlined in the problem statement, providing diagrams and commentary to illustrate my approach.

## Database Schema Design

### Task 1: Database Schema

#### Conceptual Model 
I considered the following:
> - One book can have multiple authors
> - One author can have multiple books

> - One book can have multiple editions/variations
> - A book edition has a publisher
> - A book edition has multiple copies/prints/items

> - One book copy can have a lendig status that holds information like if its borrowed, when it was, the due & return date

> - One account (librarian or patron) can borrow multiple books
> - Multiple accounts can borrow the same book from one edition (unique book copies for each patron)
> - One account has a single role of Librarian OR Patron
> - One account has a adress and contact information

![Database Schema](assets/drawSQLdesign.png)

#### Commentary:

- **Book Table:** Represents the central information about books. The relationship with the `Author` table is established through a foreign key.

- **Author Table:** Stores details about authors, allowing for a clean many-to-many relationship with the `Book` table.

- **LendingStatus Table:** Captures borrowing activities with references to the `Account` and `BookItem` tables. Fines for late returns are calculated based on predefined rates.

## Class Diagram Design

