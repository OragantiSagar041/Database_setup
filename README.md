# E‑commerce SQL Schema

A relational database schema for a basic e‑commerce system modeling Customers, Products, Categories, Orders, and OrderDetails. The design emphasizes clear entity boundaries, referential integrity, and minimal redundancy through normalization.

## Contents

- `schema.sql` — DDL to create the database and tables with keys and constraints.
- `erd/` — optional folder to store exported ERD images or design files.
- `README.md` — project documentation.

## Requirements

- Any modern SQL database (examples below cover MySQL, PostgreSQL, and SQLite).
- A SQL client (e.g., MySQL Workbench, psql/pgAdmin, SQLite CLI or GUI).

## Quick Start

### MySQL

> Notes:
> - `CREATE SCHEMA` and `CREATE DATABASE` are synonyms in MySQL; either can be used.
> - Separate `schema_postgres.sql` and `schema_sqlite.sql` files can be provided if dialect differences are required.

## ER Diagram

- MySQL Workbench: Database → Reverse Engineer (from live DB) or Reverse Engineer from Create Script, then place objects on a new EER diagram and arrange as needed. Export the diagram image to `erd/`.
- pgAdmin 4: Tools → ERD Tool → select database/tables → Generate to visualize and export as PNG/SVG into `erd/`.

## Schema Overview

- Entities:
  - Customers(CustomerID, FirstName, LastName, Email).
  - Categories(CategoryID, CategoryName).
  - Products(ProductID, ProductName, CategoryID, Price).
  - Orders(OrderID, CustomerID, OrderDate).
  - OrderDetails(OrderID, ProductID, Quantity).

- Relationships:
  - Categories 1—N Products.
  - Customers 1—N Orders.
  - Orders N—M Products via OrderDetails (composite primary key on `(OrderID, ProductID)`).

- Keys and Constraints:
  - Surrogate primary keys on entity tables (auto-increment integers).
  - Foreign keys with ON rules as needed (default shown; can add ON UPDATE/DELETE).
  - UNIQUE on `Customers.Email`.

## DDL Excerpt (MySQL)


