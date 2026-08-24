# Aggregations and Filters in SQL Queries

## 1. Introduction

Aggregations are used to perform calculations on multiple rows.

Filters are used to select only the rows that match a condition.

Common aggregation functions are:

- COUNT()
- SUM()
- AVG()
- MIN()
- MAX()

Common filtering clauses are:

- WHERE
- HAVING

---

## 2. COUNT()

COUNT() returns the number of rows.

```
SELECT COUNT(*) AS total_students
FROM students;
```

---

## 3. SUM()

SUM() returns the total value of a column.

```
SELECT SUM(salary) AS total_salary
FROM employees;
```

---

## 4. AVG()

AVG() returns the average value.

```
SELECT AVG(salary) AS average_salary
FROM employees;
```

---

## 5. MIN()

MIN() returns the smallest value.

```
SELECT MIN(salary) AS minimum_salary
FROM employees;
```
---

## 6. MAX()

MAX() returns the largest value.

```
SELECT MAX(salary) AS maximum_salary
FROM employees;
```

---

## 7. GROUP BY

GROUP BY is used to group rows with the same values.

Example:

```
SELECT department,
       COUNT(*) AS employee_count
FROM employees
GROUP BY department;
```

This returns the number of employees in each department.

---

## 8. WHERE

WHERE filters individual rows before grouping.

Example:

```
SELECT *
FROM employees
WHERE salary > 50000;
```

Only employees with a salary greater than 50,000 are returned.


---

## 9. HAVING

HAVING filters groups after GROUP BY.

Example:

```
SELECT department,
       COUNT(*) AS employee_count
FROM employees
GROUP BY department
HAVING COUNT(*) > 5;
```

Only departments with more than 5 employees are returned.

---

## 10. WHERE vs HAVING

WHERE:-
- Filters individual rows
- Used before GROUP BY
- Used to filter normal column values

HAVING:-
- Filters groups
- Used after GROUP BY
- Commonly used with aggregate functions

Example:

```
SELECT department,
       AVG(salary) AS average_salary
FROM employees
WHERE salary > 30000
GROUP BY department
HAVING AVG(salary) > 50000;
```

Here:

- WHERE :- filters employees with salary greater than 30,000.
- GROUP BY :- creates groups based on department.
- HAVING :- filters departments whose average salary is greater than 50,000.

---

## 11. DISTINCT

DISTINCT removes duplicate values.

Example:

```
SELECT DISTINCT department
FROM employees;
```

This returns each department only once.

---

## 12. Conclusion

Aggregations are used to calculate and summarize data.

Filters are used to select the required data.

The main concepts are:

- COUNT, SUM, AVG, MIN, MAX for calculations.
- WHERE for filtering rows.
- GROUP BY for grouping data.
- HAVING for filtering groups.
- DISTINCT for removing duplicates.

These concepts are commonly used together to analyze data in SQL.