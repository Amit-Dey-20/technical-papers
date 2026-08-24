# Database Isolation Levels

## 1. Introduction

Isolation Level defines how one transaction can see the changes made by another transaction.

It helps control how multiple transactions work at the same time.

SQL has four standard isolation levels:

- Read Uncommitted
- Read Committed
- Repeatable Read
- Serializable

---

## 2. Read Uncommitted

Read Uncommitted is the lowest isolation level.

A transaction can read data changed by another transaction even before it is committed.

This can cause a Dirty Read.

Example:

```text
Transaction 1 → Update balance to ₹4,000
Transaction 2 → Reads ₹4,000
Transaction 1 → ROLLBACK
```

Transaction 2 read data that was later cancelled.


---

## 3. Read Committed

Read Committed allows a transaction to read only committed data.

It prevents Dirty Reads.

Example:

```text
Transaction 1 → Update balance to ₹4,000
Transaction 2 → Waits
Transaction 1 → COMMIT
Transaction 2 → Reads ₹4,000
```

However, the same query may return different results if another transaction changes the data and commits between two reads.


---

## 4. Repeatable Read

Repeatable Read ensures that a transaction gets the same result when reading the same row multiple times within the transaction.

It prevents Dirty Reads and Non-Repeatable Reads.

Example:

```text
Transaction 1 → Read ₹5,000
Transaction 2 → Update ₹4,000 and COMMIT
Transaction 1 → Read the same row
```

Transaction 1 continues to see a consistent value according to the database's isolation behavior.

---

## 5. Serializable

Serializable is the strongest standard isolation level.

Transactions behave as if they are executed one after another.

It provides the highest level of isolation but can reduce performance because transactions may have to wait.

Example:

```text
Transaction 1 → Execute
Transaction 1 → COMMIT
Transaction 2 → Execute
Transaction 2 → COMMIT
```

---

## 6. Common Problems

Isolation levels control common transaction problems.

### Dirty Read

Reading data that another transaction has changed but not committed.

### Non-Repeatable Read

Reading the same row twice and getting different values.

### Phantom Read

Running the same query twice and getting a different set of rows.

---


## 7. Setting Isolation Level

The isolation level can be set for a transaction.

Example:

```
SET TRANSACTION ISOLATION LEVEL SERIALIZABLE;
```

Then the transaction can be started:

```
BEGIN;

SET TRANSACTION ISOLATION LEVEL SERIALIZABLE;

SELECT *
FROM accounts
WHERE account_id = 1;

COMMIT;
```

The exact behavior and supported features can vary between database systems.

---

## 8. Conclusion

Database isolation levels control how transactions interact with each other.

The four standard levels are:

- Read Uncommitted :- Lowest isolation
- Read Committed :- Prevents dirty reads
- Repeatable Read :- Prevents dirty and non-repeatable reads
- Serializable :- Strongest isolation

Higher isolation provides stronger consistency but can reduce concurrency and performance.