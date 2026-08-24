# Transactions in SQL

## 1. Introduction

A transaction is a group of SQL operations treated as one unit of work.

Transactions help keep database operations safe and reliable.

For example, transferring money between two accounts requires multiple operations that should be completed together.

---

## 2. Example of a Transaction

Suppose we transfer ₹1,000 from Account A to Account B.

```
BEGIN;

UPDATE accounts
SET balance = balance - 1000
WHERE account_id = 1;

UPDATE accounts
SET balance = balance + 1000
WHERE account_id = 2;

COMMIT;
```

Both operations are part of the same transaction.

If all operations succeed, the transaction is committed.

If an operation fails, we can cancel the transaction.

```
ROLLBACK;
```

---

## 3. BEGIN

BEGIN starts a transaction.

```
BEGIN;
```

After BEGIN, the SQL operations are performed as part of the transaction.

---

## 4. COMMIT

COMMIT permanently saves the changes made by the transaction.

```
COMMIT;
```

After COMMIT, the changes become permanent.

---

## 5. ROLLBACK

ROLLBACK cancels the current transaction and undoes its changes.

```
ROLLBACK;
```

It is useful when an operation fails or when we do not want to save the changes.

---

## 6. SAVEPOINT

A SAVEPOINT creates a point inside a transaction.

We can roll back to that point without cancelling the entire transaction.

```
BEGIN;

UPDATE accounts
SET balance = balance - 500
WHERE account_id = 1;

SAVEPOINT point1;

UPDATE accounts
SET balance = balance + 500
WHERE account_id = 2;

ROLLBACK TO point1;

COMMIT;
```

---

## 7. Transaction Properties

Transactions follow the ACID properties:

- Atomicity :- All operations succeed or none do.
- Consistency :- Database remains valid.
- Isolation :-Transactions do not improperly interfere with each other.
- Durability :- Committed changes remain saved.

---

## 8. Transaction States

A transaction can have different states:

### Active

The transaction is currently executing.

### Partially Committed

The last operation has been completed, but the changes are not yet permanently saved.

### Committed

The transaction has successfully completed and changes are saved.

### Failed

An error has occurred during the transaction.

### Aborted

The transaction has been rolled back and its changes have been cancelled.

---

## 9. Conclusion

Transactions are important for performing multiple SQL operations safely as one unit.

The main transaction commands are:

- BEGIN :- Start a transaction
- COMMIT :- Save changes
- ROLLBACK :- Cancel changes
- SAVEPOINT :- Create a rollback point

Transactions help maintain data integrity and reliability in SQL databases.