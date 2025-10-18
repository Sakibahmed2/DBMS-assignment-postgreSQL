# 🧩 PostgreSQL Assignment 7 (DBMS & PostgreSQL)

This repository contains the solution for **Assignment 7**, focused on learning and applying PostgreSQL concepts such as table creation, data insertion, and executing advanced SQL queries.  
The project demonstrates hands-on database management and query optimization for full-stack development.

---

## 📋 Assignment Overview

### 🏗️ Objective

To create and manipulate relational tables in PostgreSQL, apply constraints, insert sample data, and execute SQL queries to understand core DBMS concepts such as:

- Table creation and data insertion
- Filtering and sorting data
- Using LIMIT & OFFSET
- Aggregation with GROUP BY
- JOIN operations
- Updating records
- Working with subqueries

---

## 🗃️ Database Setup

**Database Name:** `company_db`

## Table Creation:

Create an **employees table** with the following fields:

- `employee_id` (Primary Key): Integer, unique identifier for employees.
- `employee_name`: String, representing the employee's name.
- `age`: Integer, indicating the employee's age.
- `email`: String, storing the employee's email address.
- `department_id`: Integer, referencing the department the employee belongs to.
- `salary`: Numeric, indicating the employee's salary.
- `status`: String, storing the employee's employment status.

Create a **departments table** with the following fields:

- `department_id` (Primary Key): Integer, unique identifier for departments.
- `department_name`: String, indicating the department's name.

---

## 📂 Files Included

| File Name   | Description                                                                                                        |
| ----------- | ------------------------------------------------------------------------------------------------------------------ |
| `task.sql`  | Contains all SQL statements including table creation, sample data insertion, and 7 required queries with comments. |
| `README.md` | Contains detailed explanations of PostgreSQL concepts and assignment documentation.                                |

---

## 🧠 SQL Queries Covered

1. Retrieve employees with a salary greater than 60000
2. Retrieve names of employees using LIMIT and OFFSET
3. Calculate average age of all employees
4. Retrieve employees whose emails contain `example.com`, `example.net`, or `google.com`
5. Retrieve employees who belong to the **Engineering** department
6. Update status of the employee with the **highest salary** to `'Promoted'`
7. Retrieve department name and average salary of employees per department

---

## 💬 PostgreSQL Concept Questions and Answers

### 1. What is PostgreSQL?

PostgreSQL is a powerful, open-source relational database management system (RDBMS) that supports SQL and advanced features like JSON, indexing, and ACID compliance. It’s widely used for scalable, high-performance applications.

### 2. What is the purpose of a database schema in PostgreSQL?

A schema is a logical container for tables, views, and other database objects. It helps organize data and avoid name conflicts between tables belonging to different applications or users.

### 3. Explain the primary key and foreign key concepts.

- **Primary Key:** Uniquely identifies each row in a table.
- **Foreign Key:** Establishes a relationship between two tables by referencing the primary key of another table.

### 4. What is the difference between VARCHAR and CHAR data types?

- **CHAR(n):** Fixed-length string (always uses `n` characters).
- **VARCHAR(n):** Variable-length string (uses only needed space, up to `n`).

### 5. Explain the purpose of the WHERE clause in a SELECT statement.

The `WHERE` clause filters rows based on specific conditions, allowing retrieval of only the records that meet defined criteria.

### 6. What are the LIMIT and OFFSET clauses used for?

- **LIMIT:** Restricts the number of rows returned.
- **OFFSET:** Skips a specified number of rows before starting to return rows.  
  They’re commonly used for **pagination**.

### 7. How can you perform data modification using UPDATE statements?

`UPDATE` modifies existing records in a table.  
Example:

```sql
UPDATE employees SET salary = 70000 WHERE employee_id = 5;
```

### 8. What is the significance of the JOIN operation, and how does it work in PostgreSQL?

`JOIN` combines rows from two or more tables based on related columns. It’s used to retrieve data from multiple tables in a single query.

Example:

```sql
SELECT e.employee_name, d.department_name
    FROM employees e
    JOIN departments d ON e.department_id = d.department_id;
```

### 9. Explain the GROUP BY clause and its role in aggregation operations.

`GROUP BY` groups rows sharing the same column values and allows performing aggregation functions like `COUNT`, `AVG`, `SUM`, etc.

Example:

```sql
SELECT department_id, AVG(salary) FROM employees GROUP BY department_id;
```

### 10. How can you calculate aggregate functions like COUNT, SUM, and AVG in PostgreSQL?

Aggregate functions summarize data:

```sql
SELECT COUNT(*) AS total_employees,
       SUM(salary) AS total_salary,
       AVG(salary) AS average_salary
FROM employees;
```

### 11. What is the purpose of an index in PostgreSQL, and how does it optimize query performance?

Indexes speed up data retrieval by allowing PostgreSQL to find rows faster without scanning the entire table. However, they can slightly slow down inserts/updates.

### 12. Explain the concept of a PostgreSQL view and how it differs from a table.

A view is a virtual table based on a query result. It doesn’t store data itself but provides a saved query that can be treated like a table for reading data.
