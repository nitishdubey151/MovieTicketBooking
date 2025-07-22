# 🎬 Movie Ticket Booking System - DBMS Project

This project is a database management system designed for a **Movie Ticket Booking System**. It manages the entire process of booking movie tickets, storing customer and payment information, tracking seat allocations, and handling theatre and show details. Built entirely using SQL, it demonstrates database design, normalization, and querying skills.

---

## 📌 Features

- Manage multiple **theatres**, **movies**, and **shows**
- Store **customer** information securely
- Handle **ticket booking**, **seat allocation**, and **payment**
- Execute advanced **SQL queries** to extract insights
- Designed with proper **ER diagram**, **relational schema**, and **normalization (up to BCNF)**

---

## 🗂️ Database Entities

- **Customer**
- **Movie**
- **Show**
- **Theatre**
- **Seat**
- **Ticket**
- **Payment**

---

## 🧱 Tech Stack

- **Database**: MySQL / Oracle SQL
- **Languages**: SQL (DDL, DML, DQL)
- **Tools**: SQL Developer / MySQL Workbench (for testing)

---

## 🛠️ Functionalities Implemented

- Entity-Relationship Diagram (ERD)
- Normalized schemas (3NF/BCNF)
- Table creation with proper constraints
- Data insertion using `INSERT INTO`
- Functional dependency analysis
- Complex queries including:
  - Customers who watched a specific movie
  - Payment mode analysis
  - Theatre capacity filters
  - Language-based movie analysis

---

## 📄 Sample SQL Query

```sql
-- Find the customer name who watched the movie 'Bahubali'
SELECT CUSTOMER_NAME FROM CUSTOMER
WHERE CUSTOMER_ID IN (
  SELECT CUSTOMER_ID FROM TICKET
  WHERE SHOW_ID IN (
    SELECT SHOW_ID FROM SHOW
    WHERE MOVIE_ID = (
      SELECT MOVIE_ID FROM MOVIE
      WHERE MOVIE_NAME = 'BAHUBALI'
    )
  )
);
