# SQL Joins

## 1. Introduction

A JOIN is used to combine data from two or more tables based on a related column.

For example:

```
Students
--------
student_id
name
course_id

Courses
-------
course_id
course_name
```

The course_id column connects the two tables.

---

## 2. INNER JOIN

INNER JOIN returns only the rows that have matching values in both tables.

```
SELECT students.name, courses.course_name
FROM students
INNER JOIN courses
ON students.course_id = courses.course_id;
```

Only students with a matching course are returned.

Remember: INNER JOIN = Matching rows only

---

## 3. LEFT JOIN

LEFT JOIN returns all rows from the left table and matching rows from the right table.

If there is no match, NULL is returned for the right table.

```
SELECT students.name, courses.course_name
FROM students
LEFT JOIN courses
ON students.course_id = courses.course_id;
```

Remember: LEFT JOIN = All left rows + matching right rows

---

## 4. RIGHT JOIN

RIGHT JOIN returns all rows from the right table and matching rows from the left table.

If there is no match, NULL is returned for the left table.

```
SELECT students.name, courses.course_name
FROM students
RIGHT JOIN courses
ON students.course_id = courses.course_id;
```

Remember: RIGHT JOIN = All right rows + matching left rows

---

## 5. FULL OUTER JOIN

FULL OUTER JOIN returns all rows from both tables.

If there is no match, NULL is returned for the missing side.

```
SELECT students.name, courses.course_name
FROM students
FULL OUTER JOIN courses
ON students.course_id = courses.course_id;
```

Remember: FULL OUTER JOIN = All rows from both tables

---

## 6. CROSS JOIN

CROSS JOIN returns every possible combination of rows from both tables.

If one table has 3 rows and another table has 4 rows:

```text
3 × 4 = 12 rows
```

Example:

```
SELECT students.name, courses.course_name
FROM students
CROSS JOIN courses;
```

Remember: CROSS JOIN = Every possible combination

---

## 7. SELF JOIN

A SELF JOIN joins a table with itself.

It is useful when rows in the same table are related to each other.

For example, an employee can have another employee as their manager.

```
SELECT e.name AS employee,
       m.name AS manager
FROM employees e
JOIN employees m
ON e.manager_id = m.employee_id;
```

Here, the employees table is used twice.

Remember: SELF JOIN = Table joined with itself

---

## 8. Conclusion

SQL JOINs are used to combine related data stored in different tables.

The main JOIN types are:

- INNER JOIN — Matching data
- LEFT JOIN — All left-side data
- RIGHT JOIN — All right-side data
- FULL OUTER JOIN — All data from both tables
- CROSS JOIN — All possible combinations
- SELF JOIN — A table joined with itself

JOINs are important for retrieving related information from relational databases.