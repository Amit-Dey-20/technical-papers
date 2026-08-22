# SOLID Principles

## 1. Introduction

SOLID is a set of five principles used in Object-Oriented Programming (OOPs). These principles help us write code which is:

- Easy to understand
- Easy to maintain
- Easy to test
- Easy to extend
- Less tightly coupled

SOLID stands for:
 
- S  :- Single Responsibility Principle 
- O  :- Open/Closed Principle           
- L  :- Liskov Substitution Principle   
- I  :- Interface Segregation Principle 
- D  :- Dependency Inversion Principle  

---

## 2. Single Responsibility Principle (SRP)

A class should have only one reason to change.

A class should focus on one responsibility instead of doing many unrelated tasks.

### Example
**Bad Practice**

```
class Report:
    def generate_report(self):
        print("Generating report")

    def save_to_file(self):
        print("Saving report")

    def send_email(self):
        print("Sending report by email")
```

The Report class is responsible for generating, saving, and sending the report.

**Good Practice**

```
class Report:
    def generate(self):
        print("Generating report")


class ReportSaver:
    def save(self, report):
        print("Saving report")


class EmailSender:
    def send(self, report):
        print("Sending report by email")
```

Each class now has a single responsibility.

---

# 3. Open/Closed Principle (OCP)

Software should be open for extension but closed for modification.

We should be able to add new functionality without changing existing code.

### Example
**Bad Practice**

```
class Payment:
    def pay(self, method):
        if method == "card":
            print("Paying by card")
        elif method == "cash":
            print("Paying by cash")
```

Adding another payment method requires modifying the class.

**Good Practice**

```
class Payment:
    def pay(self):
        pass


class CardPayment(Payment):
    def pay(self):
        print("Paying by card")


class CashPayment(Payment):
    def pay(self):
        print("Paying by cash")
```

Now a new payment method can be added without changing existing classes.

```
class UpiPayment(Payment):
    def pay(self):
        print("Paying by UPI")
```

---

# 4. Liskov Substitution Principle (LSP)

A child class should be usable wherever its parent class is expected.

A subclass should not break the behavior expected from its parent.

### Example
**Bad Practice**

```
class Bird:
    def fly(self):
        print("Flying")


class Penguin(Bird):
    def fly(self):
        raise Exception("Penguins cannot fly")
```

Penguin cannot properly behave like a Bird that can fly.

**Good Practice**

```
class Bird:
    pass


class FlyingBird(Bird):
    def fly(self):
        print("Flying")


class Sparrow(FlyingBird):
    pass


class Penguin(Bird):
    pass
```

Now the class hierarchy represents the actual behavior correctly.

---

# 5. Interface Segregation Principle (ISP)

A class should not be forced to implement methods it does not need.

In Python, we can use abstract classes to demonstrate this principle.

### Example
**Bad Practice**

```
class Worker:
    def work(self):
        pass

    def eat(self):
        pass


class Robot(Worker):
    def work(self):
        print("Robot working")

    def eat(self):
        pass
```

A robot does not need an eat() method.

**Good Practice**

```
class Workable:
    def work(self):
        pass


class Eatable:
    def eat(self):
        pass


class Human(Workable, Eatable):
    def work(self):
        print("Human working")

    def eat(self):
        print("Human eating")


class Robot(Workable):
    def work(self):
        print("Robot working")
```

Now each class implements only the behavior it needs.

---

# 6. Dependency Inversion Principle (DIP)

High-level classes should depend on abstractions, not concrete classes.

This reduces dependency between classes.

### Example
**Bad Practice**

```
class EmailSender:
    def send(self):
        print("Sending email")


class Notification:
    def __init__(self):
        self.sender = EmailSender()

    def notify(self):
        self.sender.send()
```

Notification is directly dependent on EmailSender.

**Good Practice**

```
class Sender:
    def send(self):
        pass


class EmailSender(Sender):
    def send(self):
        print("Sending email")


class Notification:
    def __init__(self, sender):
        self.sender = sender

    def notify(self):
        self.sender.send()
```

Now we can inject different senders:

```python
notification = Notification(EmailSender())
notification.notify()
```

The Notification class depends on the abstraction, not a specific implementation.

---

# 7. Benefits of SOLID

Following SOLID principles helps us:

* Write cleaner code
* Reduce code duplication
* Reduce coupling
* Improve testability
* Make code easier to maintain
* Add new features more easily
* Make large projects easier to manage

---

