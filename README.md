# Library Database

A relational database project implementing SQL queries for a library management system. The project models customers, books, physical book copies, loans, and customer reviews, and uses SQL to answer analytical questions about the library's data.

## Overview

The database consists of five relations:

* **Customer** — customer identifiers, names, and cities
* **Book** — book identifiers, publishers, and titles
* **BookCopy** — physical copies of books and their purchase dates
* **Loan** — records of books loaned to customers
* **Review** — customer reviews and scores for books

The project focuses on writing complex SQL queries using joins, aggregation, common table expressions (CTEs), subqueries, and self-joins.

## Queries

### 1. Summary of Books

Returns a summary for each book containing:

* Number of physical copies
* Number of loans
* Purchase date of the newest copy

This query uses joins, `COUNT`, `COUNT(DISTINCT ...)`, `MAX`, and `GROUP BY`.

### 2. Good Advice

Identifies books that a customer might be interested in based on the reading history of another customer.

A book is recommended when:

* The customer has not previously read it.
* Another customer has read all of the books read by the first customer.
* That other customer has also read the recommended book.

This query uses CTEs, cross joins, self-joins, subqueries, grouping, and `HAVING`.

### 3. Well-Received Books

Identifies books with more positive reviews than non-positive reviews.

A review is considered positive when its score is strictly greater than the reviewing customer's average score across their earlier reviews. The first review from each customer is treated as neutral.

This query uses self-joins, CTEs, conditional aggregation, and `AVG`.

### 4. Book-Age Bias

Identifies books for which each physical copy has a higher average review score than all preceding copies.

This query associates reviews with the physical copies that customers had previously borrowed, calculates average scores for each copy, and compares copies based on their purchase dates.

This query uses CTEs, joins, subqueries, aggregation, and cross joins.

## SQL Concepts Demonstrated

* Relational database design
* `JOIN` and `LEFT JOIN`
* `CROSS JOIN`
* Self-joins
* Common Table Expressions (`WITH`)
* Subqueries
* Aggregation and `GROUP BY`
* `HAVING`
* Conditional aggregation with `CASE`
* `COUNT`, `COUNT(DISTINCT ...)`, `SUM`, `AVG`, and `MAX`
* Working with temporal data
* Query decomposition and modular SQL design

## Technologies

* **Language:** SQL
* **Concepts:** Relational databases, query design, joins, aggregation, CTEs, subqueries, and analytical SQL

## Files

* [`Script.sql`](Script.sql) — SQL implementations for all four queries, including explanatory comments describing the approach used for each query.
