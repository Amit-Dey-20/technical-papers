# CAP Theorem

## 1. Introduction

CAP Theorem is a concept in distributed database systems.

It states that a distributed system can provide at most two out of three properties at the same time.

CAP stands for:

- C — Consistency
- A — Availability
- P — Partition Tolerance

---

## 2. Consistency

Consistency means that every user gets the latest and correct data.

After data is updated, all users should see the same data.

Example:
``` 
Account balance = ₹5,000
```

If the balance is changed to ₹4,000, all users should see ₹4,000.

Remember: Consistency = Same and correct data

---

## 3. Availability

Availability means that the system always responds to a request.

Even if some part of the system has a problem, the system should continue to provide a response.

Example:

```
User → Request
System → Response
```

The system should not simply stop responding.

Remember: Availability = System is always accessible

---

## 4. Partition Tolerance

Partition Tolerance means that the system continues working even when communication between some servers is lost.

In a distributed system, servers may be unable to communicate with each other because of a network failure.

Example:

```
Server A  X  Server B
```

Even though Server A and Server B cannot communicate, the system should continue operating.

Remember: Partition Tolerance = System works despite network failure

---

## 5. CAP Theorem

CAP Theorem says that when a network partition occurs, a distributed system must choose between:

- Consistency
- Availability

Partition Tolerance is required because network failures can happen in distributed systems.

Therefore, systems generally choose one of these:
```
CP → Consistency + Partition Tolerance
```

or
```
AP → Availability + Partition Tolerance
```

---

## 6. CP System

A CP system provides:

- Consistency
- Partition Tolerance

When a network partition occurs, the system may reject or delay some requests to keep the data consistent.

CP = Correct data is more important than availability.

---

## 7. AP System

An AP system provides:

- Availability
- Partition Tolerance

When a network partition occurs, the system continues responding to users.

However, different users may temporarily see different data.

The data may become consistent later.

AP = Availability is more important than immediate consistency.

---

## 8. Simple Example

Suppose two servers contain the same data:

    Server A ←→ Server B

If the network connection fails:

    Server A   X   Server B

The system has to choose:

CP:

```
Keep data consistent -> Some requests may be rejected
```

AP:

```
Keep the system available -> Some users may temporarily see different data
```


---

## 9. Conclusion

CAP Theorem is important for understanding distributed systems.

It explains the trade-off between **Consistency** and **Availability** when a network partition occurs.

In simple terms:
```
CAP = Consistency + Availability + Partition Tolerance
```

During a network partition, a distributed system must choose between maintaining strong consistency and maintaining availability.