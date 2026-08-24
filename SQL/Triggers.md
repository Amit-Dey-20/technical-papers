# Triggers in SQL

## 1. Introduction

A Trigger is a database object that automatically executes when a specific event occurs in a table.

Common events are:

- INSERT
- UPDATE
- DELETE

Triggers are useful for automatically performing actions when data changes.


---

## 2. Why are Triggers Used?

Triggers can be used to:

- Maintain audit records
- Validate data
- Automatically update related data
- Track changes
- Enforce business rules

---

## 3. Types of Triggers

Triggers can run:

- BEFORE an operation
- AFTER an operation
- INSTEAD OF an operation

They can also be triggered by:

- INSERT
- UPDATE
- DELETE

---

## 4. BEFORE Trigger

A BEFORE trigger runs before the database operation is completed.

Example:

```
CREATE OR REPLACE FUNCTION check_salary()
RETURNS TRIGGER AS $$
BEGIN
    IF NEW.salary < 0 THEN
        RAISE EXCEPTION 'Salary cannot be negative';
    END IF;

    RETURN NEW;
END;
$$ LANGUAGE plpgsql;
```

Create the trigger:

```
CREATE TRIGGER salary_check
BEFORE INSERT OR UPDATE ON employees
FOR EACH ROW
EXECUTE FUNCTION check_salary();
```

The trigger checks the salary before inserting or updating an employee.


---

## 5. AFTER Trigger

An AFTER trigger runs after the database operation is completed.

It is commonly used for logging or auditing changes.

Example:

```
CREATE OR REPLACE FUNCTION log_employee()
RETURNS TRIGGER AS $$
BEGIN
    INSERT INTO employee_log(employee_id, action)
    VALUES (NEW.employee_id, 'INSERT');

    RETURN NEW;
END;
$$ LANGUAGE plpgsql;
```

Create the trigger:

```
CREATE TRIGGER employee_log_trigger
AFTER INSERT ON employees
FOR EACH ROW
EXECUTE FUNCTION log_employee();
```

Whenever a new employee is inserted, a record is added to the log table.

**Remember:** AFTER = Runs after the operation

---

## 6. INSERT Trigger

An INSERT trigger runs when a new row is inserted.

```
CREATE TRIGGER employee_insert_trigger
AFTER INSERT ON employees
FOR EACH ROW
EXECUTE FUNCTION log_employee();
```

---

## 7. UPDATE Trigger

An UPDATE trigger runs when an existing row is updated.

```
CREATE TRIGGER employee_update_trigger
AFTER UPDATE ON employees
FOR EACH ROW
EXECUTE FUNCTION log_employee();
```

---

## 8. DELETE Trigger

A DELETE trigger runs when a row is deleted.

```
CREATE TRIGGER employee_delete_trigger
AFTER DELETE ON employees
FOR EACH ROW
EXECUTE FUNCTION log_employee();
```

---

## 9. NEW and OLD

Triggers can use NEW and OLD values.

- NEW refers to the new row.
- OLD refers to the old row.

Example:

```
CREATE OR REPLACE FUNCTION track_salary_change()
RETURNS TRIGGER AS $$
BEGIN
    INSERT INTO salary_log(employee_id, old_salary, new_salary)
    VALUES (OLD.employee_id, OLD.salary, NEW.salary);

    RETURN NEW;
END;
$$ LANGUAGE plpgsql;
```

Here:

```text
OLD.salary → Salary before the update
NEW.salary → Salary after the update
```

---

## 10. Advantages of Triggers

Triggers can:

- Automatically perform actions
- Maintain audit logs
- Enforce certain business rules
- Keep related data updated
- Track changes automatically

---

## 11. Disadvantages of Triggers

Triggers can:

- Make database logic harder to understand
- Make debugging more difficult
- Add extra processing
- Cause unexpected changes if not designed carefully

---

## 14. Conclusion

Triggers are used to automatically execute database logic when specific events occur.

They are commonly used for:

- Auditing
- Logging
- Validation
- Maintaining related data
- Enforcing business rules

Triggers can be powerful, but they should be used carefully because they can make database behavior more difficult to understand.