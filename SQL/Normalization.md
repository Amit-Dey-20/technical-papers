# Normalization in SQL

## 1. Introduction

Normalization is a process of organizing data in a database to reduce duplicate data and improve data consistency.

It divides large tables into smaller related tables.

The main goals of normalization are:

- Reduce data duplication
- Avoid data inconsistency
- Make data easier to manage
- Improve database structure

---

## 2. Why is Normalization Needed?

Suppose we have a table:

```text
Student_ID | Student_Name | Course | Teacher
-----------|--------------|--------|--------
1          | Amit         | SQL    | Rahul
2          | Priya        | SQL    | Rahul
3          | John         | Python | Anil
```

Here, the teacher name Rahul is repeated.

If the teacher's name needs to be changed, we may have to update multiple rows.

Normalization helps avoid this problem by dividing the data into related tables.

---

## 3. First Normal Form (1NF)

A table is in First Normal Form (1NF) when:

- Each column contains a single value.
- There are no repeating groups.
- Each row is unique.

### Example

Not in 1NF:

```text
Student_ID | Student_Name | Courses
-----------|--------------|----------------
1          | Amit         | SQL, Python
```

The Courses column contains multiple values.

After applying 1NF:

```text
Student_ID | Student_Name | Course
-----------|--------------|--------
1          | Amit         | SQL
1          | Amit         | Python
```


---

## 4. Second Normal Form (2NF)

A table is in Second Normal Form (2NF) when:

- It is already in 1NF.
- Every non-key column depends on the entire primary key.

2NF mainly deals with partial dependency.

### Example

Suppose:

```text
Student_ID | Course_ID | Student_Name | Course_Name
-----------|-----------|--------------|------------
1          | 101       | Amit         | SQL
2          | 102       | Priya        | Python
```

Here, Student_Name depends only on Student_ID, and Course_Name depends only on Course_ID.

The table can be divided into:

```text
Students
-----------------------
Student_ID | Student_Name

Courses
-----------------------
Course_ID | Course_Name

Enrollments
-----------------------
Student_ID | Course_ID
```


---

## 5. Third Normal Form (3NF)

A table is in Third Normal Form (3NF) when:

- It is already in 2NF.
- Non-key columns should not depend on other non-key columns.

This removes transitive dependency.

### Example

Suppose:

```text
Employee_ID | Employee_Name | Department_ID | Department_Name
------------|---------------|---------------|----------------
1           | Amit          | 10            | IT
2           | Priya         | 20            | HR
```

Department_Name depends on Department_ID, not directly on Employee_ID.

We can divide the table into:

```text
Employees
----------------------------
Employee_ID | Employee_Name | Department_ID

Departments
----------------------------
Department_ID | Department_Name
```

---

## 6. Boyce-Codd Normal Form (BCNF)

BCNF is a stronger version of 3NF.

A table is in BCNF when every determinant is a candidate key.

BCNF is used when 3NF still allows certain types of dependency problems.

For most basic database designs, understanding 1NF, 2NF, and 3NF is usually sufficient.

---

## 7. Normalization Example

Consider this table:

```text
Student_ID | Student_Name | Course_ID | Course_Name
-----------|--------------|-----------|------------
1          | Amit         | 101       | SQL
2          | Priya        | 102       | Python
3          | John         | 101       | SQL
```

Instead of storing repeated course information, we can create separate tables.

### Students

```text
Student_ID | Student_Name
-----------|-------------
1          | Amit
2          | Priya
3          | John
```

### Courses

```text
Course_ID | Course_Name
----------|------------
101       | SQL
102       | Python
```

### Enrollments

```text
Student_ID | Course_ID
-----------|----------
1          | 101
2          | 102
3          | 101
```

The tables can be connected using keys.

---

## 8. Advantages of Normalization

Normalization provides several benefits:

- Reduces duplicate data
- Prevents data inconsistency
- Makes updates easier
- Improves data organization
- Reduces unnecessary storage
- Makes relationships between data clearer

---

## 9. Disadvantages of Normalization

Highly normalized databases may require more tables and more `JOIN` operations.

This can sometimes make queries more complex.

Therefore, databases should be normalized according to the requirements of the application.

---

## 10. Conclusion

Normalization is an important database design technique.

It organizes data into smaller related tables and reduces unnecessary duplication.

The main normal forms are:

- 1NF :- Removes repeating and multiple values.
- 2NF :- Removes partial dependencies.
- 3NF :- Removes transitive dependencies.
- BCNF :- Provides stronger normalization rules.

Normalization helps create a database that is organized, consistent, and easier to maintain.