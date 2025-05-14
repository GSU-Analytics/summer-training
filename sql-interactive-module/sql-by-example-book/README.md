# Oracle SQL Training: Intermediate to Advanced Reporting

This training is intended for experienced users of Oracle SQL Developer who query databases for analytical reporting. The lessons are taken from focus [Oracle SQL by Example 4th Edition](https://www.oreilly.com/library/view/oracle-sql-by/9780137047345/) and focus on on writing efficient, professional-grade SQL for multi-table reporting and advanced data manipulation. 

## Setup Instructions

**Install the STUDENT Sample Schema**

* Follow steps in `readme.pdf`, Sections I–II, pp. 1–5
* Run `createStudent.sql` to build schema
* Use `rebuildStudent.sql` or `dropStudent.sql` as needed
* Add supplemental tables using `sql_book_add_tables.sql`

## Warm-Up: Single-Table Operations Review

**Goal**: Refresh SELECT basics using one real-world table (`COURSE` or `STUDENT`)

* SELECT specific and all columns
* Filtering with `WHERE`, `BETWEEN`, `IN`, `LIKE`, `IS NULL`
* Sorting with `ORDER BY`
* Column aliasing
* Using arithmetic in SELECT
* Applying built-in functions (`UPPER`, `ROUND`, `NVL`, etc.)
* Reference: Chapters 2–3, pp. 49–101

## Aggregate Queries and GROUP BY Logic

* **Lab 6.1**: Aggregates – `SUM`, `COUNT`, `AVG`, `MIN`, `MAX`, `COUNT(DISTINCT)`
* **Lab 6.2**: Grouping & Filtering – `GROUP BY`, `HAVING`, `GROUPING SETS`, `ROLLUP`, `CUBE`
* Reference: Chapter 6, pp. 263–283

## Joins

* **Lab 7.1–7.2**:

  * Equijoins, inner joins
  * OUTER JOINs (LEFT, RIGHT, FULL)
  * Cross joins and Cartesian products
  * ANSI vs Oracle `(+)` syntax
  * Multicolumn joins and self-joins
* Reference: Chapter 7 & 10, pp. 285–427

## Subqueries

* **Lab 8.1–8.4**:

  * Scalar, multicolumn, and nested subqueries
  * Correlated subqueries and EXISTS/NOT EXISTS
  * Scalar subquery expressions in `SELECT`, `ORDER BY`, `CASE`
  * ANY, ALL, and performance notes
* Reference: Chapter 8, pp. 323–376

## Single-Row Built-In Functions

* **Character Functions**: `UPPER`, `LOWER`, `INITCAP`, `SUBSTR`, `INSTR`, `TRIM`, `LPAD`
* **Number Functions**: `ROUND`, `TRUNC`, `MOD`, `FLOOR`, `CEIL`
* **Conversion Functions**: `TO_CHAR`, `TO_DATE`, `CAST`, `TO_NUMBER`
* **Null Handling**: `NVL`, `NVL2`, `COALESCE`, `NULLIF`, `LNNVL`
* **Conditional Logic**: `DECODE`, `CASE`
* Reference: Chapter 4, pp. 133–187

## Date and Time Logic

* **Working with DATE**:

  * `SYSDATE`, `CURRENT_DATE`, `SYSTIMESTAMP`, `TRUNC(date)`
  * `ROUND(date)`, `EXTRACT`, intervals
  * Implicit vs explicit conversion
  * Time zones, format masks, `TO_DATE`, `TO_CHAR`
* Reference: Chapter 5, pp. 189–261

## Set Operators

* **UNION vs UNION ALL**
* **INTERSECT**, **MINUS**
* Sort order, data types, NULL handling
* When to use vs joins/subqueries
* Reference: Chapter 9, pp. 377–397

## Analytical Functions & CTEs

* **Window Functions**:

  * `ROW_NUMBER`, `RANK`, `DENSE_RANK`, `NTILE`
  * `LAG`, `LEAD`, `FIRST_VALUE`, `LAST_VALUE`
  * `PARTITION BY`, `ORDER BY`, `ROWS BETWEEN`
* **WITH Clause / CTEs**:

  * Modular query design
  * Nesting and chaining WITH clauses
* Reference: Chapter 17, Lab 17.1, pp. 741–781
