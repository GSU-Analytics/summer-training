# Quick Start Guide to SQL - Course Summary

This document summarizes the LinkedIn Learning course [Quick Start Guide to SQL](https://www.linkedin.com/learning/quick-start-guide-to-sql), which provides a comprehensive introduction to SQL fundamentals with a focus on Oracle SQL syntax.

## Table of Contents

1. [Basic SELECT Statements](#basic-select-statements)
2. [Operators](#operators)
3. [Data Types](#data-types)
4. [Comparison Conditions](#comparison-conditions)
5. [Logical Conditions](#logical-conditions)
6. [Order of Precedence](#order-of-precedence)
7. [Sorting Data](#sorting-data)
8. [Types of Functions and Number Functions](#types-of-functions-and-number-functions)
9. [Character Functions](#character-functions)
10. [Date Functions](#date-functions)
11. [Data Type Conversion Functions](#data-type-conversion-functions)
12. [Conditional Functions](#conditional-functions)
13. [Types of Group Functions](#types-of-group-functions)
14. [Creating Groups and Nested Groups](#creating-groups-and-nested-groups)
15. [Filtering Group Results](#filtering-group-results)
16. [Types of Joins](#types-of-joins)
17. [Uses of Subqueries](#uses-of-subqueries)
18. [Types of Subqueries](#types-of-subqueries)

## Basic SELECT Statements

The SELECT statement is used to fetch data from database tables based on specified criteria.

**Key Concepts:**
- Basic syntax: `SELECT [columns] FROM [table]`
- Using `*` to fetch all columns vs. specifying individual columns
- SQL is not case-sensitive but the standard practice is uppercase for keywords
- Proper indentation improves readability for complex queries
- SELECT statements are used to:
  - Fetch data from specific columns in a table
  - Fetch data from one or multiple tables
  - Filter rows based on search criteria

## Operators

SQL supports various operators for data manipulation and calculations.

**Key Concepts:**
- **Arithmetic operators**: +, -, *, /
- **Character string operators**: || (concatenation), single quotes, double quotes
- **Order of precedence**: Multiplication and division before addition and subtraction
- Using parentheses to override standard precedence
- NULL values in expressions result in NULL (not zero or blank space)
- Column aliases using AS keyword

## Data Types

SQL supports various data types for storing different kinds of information.

**Key Concepts:**
- **VARCHAR2**: Variable-length character data (max 4,000 characters)
- **CHAR**: Fixed-length character data (max 2,000 characters)
- **NUMBER**: Numeric data with precision (P) and scale (S)
- **DATE**: For date and time values
- **LONG**: Variable-length character data up to 2GB
- **CLOB**: Character data up to 4GB
- **RAW**: Raw binary data up to 2,000 bytes
- **LONG RAW**: Raw binary data up to 2GB
- **BLOB**: Binary large objects up to 4GB
- **BFILE**: External file location up to 4GB
- **ROWID**: Unique address of a row in a table

## Comparison Conditions

These conditions are used to filter data in the WHERE clause.

**Key Concepts:**
- Basic comparison operators: =, >, >=, <, <=, !=
- Using single quotes for character values (case-sensitive)
- Date format in conditions (single quotes required)
- **BETWEEN AND**: Checks if a value is within a range (inclusive)
- **IN**: Checks if a value matches any in a given set
- **LIKE**: Checks for character patterns
  - `%` represents any sequence of characters
  - `_` represents a single character
- **IS NULL / IS NOT NULL**: Checks for NULL values

## Logical Conditions

Logical conditions are used to combine multiple conditions in the WHERE clause.

**Key Concepts:**
- **AND**: Returns TRUE only when both conditions are TRUE
- **OR**: Returns TRUE if at least one condition is TRUE
- **NOT**: Negates the condition (returns TRUE if the condition is FALSE)
- Truth tables for each logical operator
- Handling NULL values with logical operators

## Order of Precedence

Understanding the evaluation order of different operators and conditions.

**Key Concepts:**
- Execution order: Arithmetic operators → Concatenation → Comparison → IS NULL/NOT NULL → LIKE/IN → BETWEEN → NOT → AND → OR
- Using parentheses to change the default precedence
- Examples showing different results with and without parentheses

## Sorting Data

Organizing query results in a specific order.

**Key Concepts:**
- **ORDER BY** clause for sorting data
- Default sorting is ascending (ASC)
- Explicit DESC for descending order
- Sorting by multiple columns
- Sorting rules for different data types:
  - Numbers: least to greatest
  - Characters: A to Z
  - Dates: earliest to latest
  - NULL values appear last in ascending order, first in descending order

## Types of Functions and Number Functions

Functions perform specific operations on data.

**Key Concepts:**
- **Single row functions**: Work on one row at a time, return one result per row
- **Multiple row functions**: Work on groups of rows, return one result per group
- **Number functions**:
  - ROUND: Rounds to specified decimal places
  - TRUNC: Truncates to specified decimal places
  - MOD: Returns remainder of division

## Character Functions

Functions that manipulate character data.

**Key Concepts:**
- **Case manipulation functions**:
  - LOWER: Converts to lowercase
  - UPPER: Converts to uppercase
  - INITCAP: Converts to initial capital (camel case)
- **Character manipulation functions**:
  - CONCAT: Joins strings
  - SUBSTRING: Extracts a portion of a string
  - LENGTH: Counts characters in a string
  - INSTRING: Returns position of a substring
  - LPAD/RPAD: Pads strings with specified characters
  - TRIM: Removes specified characters
  - REPLACE: Replaces occurrences of a substring

## Date Functions

Functions for working with date values.

**Key Concepts:**
- **SYSDATE**: Returns current date
- Date arithmetic operations
- **MONTHS_BETWEEN**: Calculates months between dates
- **ADD_MONTHS**: Adds specified months to a date
- **NEXT_DAY**: Finds next occurrence of a specified day
- **LAST_DAY**: Returns last day of the month
- **ROUND**: Rounds date to nearest month/year
- **TRUNC**: Truncates date to first day of month/year

## Data Type Conversion Functions

Functions that convert data from one type to another.

**Key Concepts:**
- **Implicit conversion**: Automatic conversion by Oracle Server
- **Explicit conversion functions**:
  - TO_CHAR: Converts number/date to character format
  - TO_NUMBER: Converts character to number
  - TO_DATE: Converts character to date
- **General functions**:
  - NVL: Converts NULL to a specified value
  - NULLIF: Returns NULL if two expressions are equal
  - COALESCE: Returns first non-NULL expression

## Conditional Functions

Functions that implement conditional logic in SQL.

**Key Concepts:**
- **CASE**: Implements IF-THEN-ELSE logic
  - Simple CASE expressions
  - Searched CASE expressions
- **DECODE**: Oracle's proprietary alternative to CASE
- Practical examples of using conditional functions

## Types of Group Functions

Functions that operate on groups of rows.

**Key Concepts:**
- Group functions return one result per group
- **SUM**: Calculates total of values
- **AVG**: Calculates average of values
- **COUNT**: Counts rows or non-NULL values
- **MAX**: Returns maximum value
- **MIN**: Returns minimum value
- **VARIANCE** and **STDDEV**: Statistical functions
- Data type compatibility with group functions

## Creating Groups and Nested Groups

Organizing data into logical groups for analysis.

**Key Concepts:**
- **GROUP BY** clause for creating row groups
- Syntax and placement in SELECT statement
- Rules for using GROUP BY:
  - Columns in SELECT that are not in group functions must be in GROUP BY
  - Cannot use column aliases in GROUP BY
- Grouping by multiple columns

## Filtering Group Results

Specifying conditions for groups rather than individual rows.

**Key Concepts:**
- Cannot use group functions in WHERE clause
- **HAVING** clause for filtering groups
- Proper order of clauses: SELECT → FROM → WHERE → GROUP BY → HAVING → ORDER BY
- Practical examples of filtering groups

## Types of Joins

Combining data from multiple tables.

**Key Concepts:**
- Syntax for joins
- **Inner join**: Returns only matching rows from both tables
- **Left join**: Returns all rows from left table and matching rows from right table
- **Right join**: Returns all rows from right table and matching rows from left table
- **Full outer join**: Returns all rows from both tables
- Visual representation using Venn diagrams
- Practical examples of different join types

## Uses of Subqueries

Using a query within another query.

**Key Concepts:**
- Subqueries (inner queries) are executed first
- Rules for subqueries:
  - Must be enclosed in parentheses
  - Must be on the right side of comparison conditions

## Types of Subqueries

Different types of subqueries based on the rows returned.

**Key Concepts:**
- **Single-row subqueries**: Return one row/value
  - Use with single-row comparison operators (=, !=, >, <, >=, <=)
  - Can use group functions in subqueries
- **Multiple-row subqueries**: Return multiple rows
  - Use with multiple-row operators (IN, ANY, ALL)
  - IN: Matches any value in the list
  - ANY: Compares with at least one value in the list
  - ALL: Compares with all values in the list

## Next Steps

The instructor recommends the "SQL Queries Made Easy" course as a follow-up, which covers:
- Creating, altering, and dropping tables
- Adding, manipulating, and deleting data