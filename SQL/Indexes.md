# Indexes in SQL

## 1. Introduction

An index is a database object used to make data retrieval faster.

It works like an index in a book.

Instead of checking every row in a table, the database can use an index to find the required data quickly.

---

## 2. Why are Indexes Used?

Suppose we have a table with thousands of employees.

```
SELECT *
FROM employees
WHERE employee_id = 1000;
```

Without an index, the database may need to check many rows.

With an index on employee_id, the database can find the required row faster.


---

## 3. Creating an Index

The CREATE INDEX statement is used to create an index.

```
CREATE INDEX idx_employee_name
ON employees(name);
```

This creates an index on the name column.

---

## 4. Unique Index

A unique index does not allow duplicate values in the indexed column.

```
CREATE UNIQUE INDEX idx_employee_email
ON employees(email);
```

This ensures that the same email cannot appear more than once.

---

## 5. Composite Index

A composite index is an index created on two or more columns.

```
CREATE INDEX idx_employee_dept_salary
ON employees(department, salary);
```

This can be useful when queries commonly use both columns.

Example:

```
SELECT *
FROM employees
WHERE department = 'IT'
AND salary > 50000;
```

---

## 6. Dropping an Index

An index can be removed using DROP INDEX.

```
DROP INDEX idx_employee_name;
```

This removes the index from the database.

---

## 7. Advantages of Indexes

Indexes provide several benefits:

- Make data retrieval faster
- Improve search performance
- Improve filtering performance
- Improve some JOIN operations
- Improve sorting in some queries

---

## 8. Disadvantages of Indexes

Indexes also have some disadvantages:

- They require additional storage.
- They can slow down INSERT operations.
- They can slow down UPDATE operations.
- They can slow down DELETE operations.

This happens because the database must also maintain the index when data changes.

---

## 9. When to Use Indexes

Indexes are useful for columns that are frequently used in:

- WHERE
- JOIN
- ORDER BY
- GROUP BY

Example:

```
SELECT *
FROM employees
WHERE department = 'IT';
```

An index on department may improve the performance of this query.

---

## 10. Primary Key and Index

A Primary Key is normally indexed automatically by the database system.

Example:

```
CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(100)
);
```

The primary key helps uniquely identify each row and is typically backed by an index.

---

## 11. Conclusion

Indexes are used to improve the performance of database queries.

They are especially useful for columns frequently used for searching, joining, filtering, and sorting.

However, indexes require additional storage and can make data modification operations slower.

Therefore, indexes should be created carefully based on query requirements.