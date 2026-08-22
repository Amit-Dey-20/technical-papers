# Object-Oriented Programming in Python

# 1. Introduction

Object-Oriented Programming (OOP) is a programming approach where programs are designed using classes and objects.

OOP helps organize code by combining data (attributes) and behavior (methods) into objects.

---

# 2. Class

A class is a blueprint or template used to create objects.

### Example

```
class Student:
    pass
```

Here, Student is a class.

---

# 3. Object

An object is an instance of a class.

### Example

```
class Student:
    pass

student1 = Student()

print(student1)
```

Here, student1 is an object of the Student class.

---

# 4. Attributes

Attributes are variables that store the data or properties of an object.

### Example

```
class Student:

    def __init__(self, name, age):
        self.name = name
        self.age = age


student = Student("Amit", 22)

print(student.name)
print(student.age)
```

Here, name and age are attributes.

---

# 5. Methods

A method is a function defined inside a class that represents an object's behavior.

### Example

```
class Student:

    def study(self):
        print("Student is studying")


student = Student()
student.study()
```

---

# 6. self

self represents the current object and is used to access its attributes and methods.

---

# 7. Constructor

A constructor is a special method that runs automatically when an object is created.

In Python, __init__() is commonly used as the constructor.

### Example

```
class Student:

    def __init__(self):
        print("Student created")


student = Student()
```

Output:

```
Student created
```

---

# 8. Instance Attribute

An instance attribute belongs to a particular object.

### Example

```
class Student:

    def __init__(self, name):
        self.name = name

student1 = Student("Amit")
student2 = Student("Rahul")

print(student1.name)
print(student2.name)
```

Output:

```
Amit
Rahul
```

---

# 9. Class Attribute

A class attribute belongs to the class and can be shared by its objects.

### Example

```
class Student:

    school = "ABC School"


student1 = Student()

print(student1.school)
```

Output:

```
ABC School
```

---

# 10. Encapsulation

Encapsulation means combining data and methods inside a class and controlling access to the data.

### Example

```
class BankAccount:

    def __init__(self, balance):
        self.balance = balance

    def deposit(self, amount):
        self.balance += amount


account = BankAccount(1000)
account.deposit(500)

print(account.balance)
```

---

# 11. Public Attribute

A public attribute can be accessed directly from outside the class.

---

# 12. Protected Attribute

A protected attribute starts with a single underscore _. It indicates that the attribute is intended for internal or subclass use.

---

# 13. Private Attribute

A private attribute starts with double underscores __. Python uses name mangling for such attributes.

---

# 14. Getter

A getter is a method used to retrieve the value of an attribute.

### Example

```
class Student:

    def __init__(self, marks):
        self.__marks = marks

    def get_marks(self):
        return self.__marks


student = Student(90)

print(student.get_marks())
```

---

# 15. Setter

A setter is a method used to modify the value of an attribute.

### Example

```
class Student:

    def __init__(self, marks):
        self.__marks = marks

    def set_marks(self, marks):
        self.__marks = marks
```

---

# 16. Inheritance

Inheritance allows a child class to reuse attributes and methods of a parent class.

### Example

```
class Animal:

    def eat(self):
        print("Eating")


class Dog(Animal):
    pass


dog = Dog()
dog.eat()
```

Here, Dog inherits from Animal.

---

# 17. Types of Inheritance

## 17.1 Single Inheritance

One child class inherits from one parent class.

```
Animal
   |
  Dog
```

### Example

```
class Animal:
    pass


class Dog(Animal):
    pass
```

---

## 17.2 Multiple Inheritance

One child class inherits from multiple parent classes.

```
Father     Mother
   \         /
    \       /
     Child
```

### Example

```
class Father:
    pass


class Mother:
    pass


class Child(Father, Mother):
    pass
```

---

## 17.3 Multilevel Inheritance

A class inherits from another child class, creating multiple levels.

```
Animal
   |
 Mammal
   |
  Dog
```

### Example

```
class Animal:
    pass


class Mammal(Animal):
    pass


class Dog(Mammal):
    pass
```

---

## 17.4 Hierarchical Inheritance

Multiple child classes inherit from the same parent class.

```
      Animal
      /    \
    Dog    Cat
```

### Example

```
class Animal:
    pass


class Dog(Animal):
    pass


class Cat(Animal):
    pass
```

---

## 17.5 Hybrid Inheritance

Hybrid inheritance is a combination of two or more types of inheritance.

---

# 18. Method Overriding

Method overriding occurs when a child class provides its own implementation of a parent class method.

### Example

```
class Animal:

    def sound(self):
        print("Animal sound")


class Dog(Animal):

    def sound(self):
        print("Bark")


dog = Dog()
dog.sound()
```

Output:

```text
Bark
```

---

# 19. super()

super() is used to access methods or the constructor of the parent class.

### Example

```
class Animal:

    def sound(self):
        print("Animal sound")


class Dog(Animal):

    def sound(self):
        super().sound()
        print("Bark")


dog = Dog()
dog.sound()
```

---

# 20. Polymorphism

Polymorphism means the same method name can behave differently for different objects.

### Example

```
class Dog:

    def sound(self):
        print("Bark")


class Cat:

    def sound(self):
        print("Meow")


Dog().sound()
Cat().sound()
```

Output:

```
Bark
Meow
```

---

# 21. Abstraction

Abstraction means hiding unnecessary implementation details and showing only the required functionality.

Python provides the abc module for implementing abstraction.

### Example

```
from abc import ABC, abstractmethod


class Animal(ABC):

    @abstractmethod
    def sound(self):
        pass


class Dog(Animal):

    def sound(self):
        print("Bark")
```

---

# 22. Association

Association represents a relationship between two independent objects.

### Example

```
class Teacher:
    pass


class Student:
    pass


teacher = Teacher()
student = Student()
```

The teacher and student objects can exist independently.

---

# 23. Composition

Composition means creating a relationship where one object contains another object.

It represents a HAS-A relationship.

### Example

```
class Engine:

    def start(self):
        print("Engine started")


class Car:

    def __init__(self):
        self.engine = Engine()


car = Car()
car.engine.start()
```

Here:

```text
Car HAS-A Engine
```

---

# 24. Aggregation

Aggregation is a weak relationship where one object contains another object, but both can exist independently.

### Example

```
class Student:

    def __init__(self, name):
        self.name = name


class School:

    def __init__(self, student):
        self.student = student


student = Student("Amit")
school = School(student)
```

The student object can exist without the school object.

---

# 25. Class Method

A class method works with the class instead of a particular object.

It uses the @classmethod decorator.

### Example

```
class Student:

    school = "ABC School"

    @classmethod
    def get_school(cls):
        return cls.school


print(Student.get_school())
```

---

# 26. Static Method

A static method is a method that does not require self.

It uses the @staticmethod decorator.

### Example

```
class Calculator:

    @staticmethod
    def add(a, b):
        return a + b


print(Calculator.add(10, 20))
```

Output:

```
30
```

---

# 27. Property

A property allows a method to be accessed like an attribute.

It uses the @property decorator.

### Example

```
class Student:

    def __init__(self, name):
        self._name = name

    @property
    def name(self):
        return self._name


student = Student("Amit")

print(student.name)
```

---

# 28. Magic / Dunder Methods

Magic methods are special methods with double underscores before and after their names.

Examples:

```
__init__()
__str__()
__len__()
__add__()
```
---

