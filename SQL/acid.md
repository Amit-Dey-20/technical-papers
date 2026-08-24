# ACID Properties in SQL

## 1. Introduction

ACID is a set of four properties that make database transactions reliable and safe.

ACID stands for:

- A — Atomicity
- C — Consistency
- I — Isolation
- D — Durability

---

## 2. Transaction

All the operations done by using DML commands is known as transaction.

For example, transferring ₹1,000 from one account to another:
    
```
BEGIN:

UPDATE accounts
SET balance = balance - 1000
WHERE account_id = 1;

UPDATE accounts
SET balance = balance + 1000
WHERE account_id = 2;

COMMIT;
```

If any operation fails, the transaction can be cancelled using:
```
ROLLBACK;
```
---

## 3. Atomicity

Atomicity means all or nothing.

All operations in a transaction must succeed. If one operation fails, all changes are cancelled.

Example:
```
Account A: ₹5,000 → ₹4,000
Account B: ₹3,000 → ₹4,000
```

If the second operation fails, the first operation is also cancelled.

Remember: Atomicity = All or Nothing

---

## 4. Consistency

Consistency means the database must remain valid after a transaction.

A transaction must follow rules such as:

- Primary Key
- Foreign Key
- NOT NULL
- UNIQUE
- CHECK

Example:
```
balance NUMERIC CHECK (balance >= 0)
```

This prevents the balance from becoming negative.

Remember: Consistency = Database remains valid

---

## 5. Isolation

Isolation means transactions running at the same time should not incorrectly affect each other.

For example:

    
    
```
Transaction 1 → Withdraw ₹1,000
Transaction 2 → Withdraw ₹2,000
```

The database manages both transactions correctly.

Remember: Isolation = Transactions work independently

---

## 6. Durability

Durability means committed data is permanently saved.

After:
```
COMMIT;
```

the changes should remain saved even if:

- The system crashes
- The database restarts
- There is a power failure

Remember: Durability = Committed data stays saved

---

## 7. Transaction Commands


- BEGIN :- Starts a transaction
- COMMIT :- Saves the transaction
- ROLLBACK :- Cancels the transaction
- SAVEPOINT :- Creates a rollback point

Example:
    
```
BEGIN;
UPDATE accounts
SET balance = balance - 1000
WHERE account_id = 1;
COMMIT;

```

---

## 8. Isolation Levels

SQL provides four standard isolation levels:

- Read Uncommitted :- Can read uncommitted data.
- Read Committed :- Reads only committed data.
- Repeatable Read :- Gives consistent results for repeated reads.
- Serializable :- Strongest isolation level.

---

## 9. Conclusion

ACID properties make database transactions reliable and safe.

They ensure that transactions are completed correctly, database rules are maintained, concurrent transactions are handled safely, and committed data is not lost.