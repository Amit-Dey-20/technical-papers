# Locking Mechanism in SQL

## 1. Introduction

A locking mechanism is used by a database to control access to data when multiple transactions work at the same time.

Locks help prevent two transactions from making conflicting changes to the same data.


---

## 2. Why is Locking Needed?

Suppose two users try to update the same account at the same time.

```text
Transaction 1 → Update Account A
Transaction 2 → Update Account A
```

Without proper locking, one transaction may overwrite the changes made by another transaction.

Locking helps the database manage such situations safely.

---

## 3. Shared Lock

A Shared Lock allows multiple transactions to read the same data.

However, the data cannot be modified while the shared lock is active.

Example:

```
SELECT *
FROM accounts
WHERE account_id = 1
FOR SHARE;
```

Multiple transactions can read the data, but they cannot modify it until the lock is released.


---

## 4. Exclusive Lock

An Exclusive Lock is used when a transaction wants to modify data.

Only one transaction can hold an exclusive lock on the same data at a time.

Example:

```
SELECT *
FROM accounts
WHERE account_id = 1
FOR UPDATE;
```

This prevents other transactions from modifying the locked row until the lock is released.

---

## 5. Row-Level Lock

A Row-Level Lock locks specific rows instead of the entire table.

Example:

```
SELECT *
FROM accounts
WHERE account_id = 1
FOR UPDATE;
```

Only the selected row is locked.

This allows other transactions to work with different rows.

---

## 6. Table-Level Lock

A Table-Level Lock locks an entire table.

Example:

```
LOCK TABLE accounts IN EXCLUSIVE MODE;
```

Other transactions may be restricted from performing certain operations on the table while the lock is active.

---

## 7. Deadlock

A deadlock occurs when two transactions wait for each other to release locks.

Example:

```text
Transaction 1 → Locks Row A → Waits for Row B

Transaction 2 → Locks Row B → Waits for Row A
```

Neither transaction can continue.

The database detects the deadlock and normally cancels one of the transactions.


---

## 8. Lock Release

Locks are generally released when the transaction ends.

```
COMMIT;
```

or:

```
ROLLBACK;
```

After the transaction ends, the locks held by that transaction are released.

---

## 9. Advantages of Locking

Locking helps to:

- Prevent conflicting updates
- Protect data consistency
- Manage concurrent transactions
- Prevent lost updates
- Control access to shared data

---

## 10. Conclusion

Locking is an important mechanism used by databases to safely handle multiple transactions.

The main concepts are:

- Shared Lock :- Used mainly for reading.
- Exclusive Lock :- Used for modifying data.
- Row-Level Lock :- Locks specific rows.
- Table-Level Lock :- Locks the entire table.
- Deadlock :- Occurs when transactions wait for each other.

Proper locking helps maintain data consistency and safe concurrent access in SQL databases.