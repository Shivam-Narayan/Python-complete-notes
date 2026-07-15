# Python Object-Oriented and Core Concepts

This reference document covers essential Python topics with clear definitions, practical examples, and a professional structure.

---

## 1. Class

A class is a blueprint for creating objects. It defines the data attributes and behaviors that objects of that type will have.

### Syntax

```python
class ClassName:
    pass
```

### Example

```python
class Car:
    pass
```

A class groups related state and behavior so it can be reused consistently.

---

## 2. Object

An object is an instance of a class. It represents a concrete entity with the state and behavior defined by the class.

### Example

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def greet(self):
        return f"Hello, my name is {self.name}."

person = Person("Alice", 30)
print(person.name)
print(person.greet())
```

Objects hold attributes and methods that operate on those attributes.

---

## 3. self

In instance methods, `self` is a reference to the current object. It is the conventional name for the first parameter of an instance method.

### Example

```python
class Student:
    def __init__(self, name):
        self.name = name

    def display(self):
        print(self.name)

obj = Student("Shivam")
obj.display()
```

Python automatically passes the current object as the first argument when calling an instance method.

---

## 4. Constructor (`__init__`)

The constructor initializes a new object when it is created. In Python, this is implemented with the `__init__` method.

### Example

```python
class Car:
    def __init__(self):
        print("Car created")

obj = Car()
```

The constructor runs automatically at instantiation and sets up the object's initial state.

---

## 5. `__str__`

The `__str__` method returns a human-readable string representation of an object. It is used by `print()` and `str()`.

### Example

```python
class Car:
    def __init__(self, brand, model):
        self.brand = brand
        self.model = model

    def __str__(self):
        return f"{self.brand} {self.model}"

car = Car("Toyota", "Corolla")
print(car)
print(str(car))
```

Without `__str__`, printing an object shows a generic memory address representation.

---

## 6. Encapsulation

Encapsulation bundles data and methods inside a class and hides internal state from outside access.

### Why it matters
- Protects internal data from unintended modification
- Provides a controlled interface for access
- Centralizes validation and business logic

### Example

```python
class Employee:
    def __init__(self):
        self.__salary = 0

    def set_salary(self, salary):
        self.__salary = salary

    def get_salary(self):
        return self.__salary

employee = Employee()
employee.set_salary(50000)
print(employee.get_salary())
```

Private attributes are name-mangled by Python to discourage external access.

---

## 7. Inheritance

Inheritance allows a class to derive properties and behaviors from another class.

### Definition
A child class inherits from a parent class and can reuse or extend its implementation.

### Example

```python
class Animal:
    def sound(self):
        print("Animal makes a sound")

class Dog(Animal):
    pass

obj = Dog()
obj.sound()
```

### Inherited members
A subclass inherits:
- instance variables
- methods
- constructors (unless overridden)

```python
class Employee:
    def __init__(self):
        self.company = "Google"

    def display(self):
        print("Welcome")

class Developer(Employee):
    pass

developer = Developer()
print(developer.company)
developer.display()
```

### Benefits
- Reduces duplicate code
- Organizes related behavior
- Enables polymorphic design

---

## 8. Types of Inheritance

### 8.1 Single inheritance
One subclass inherits from one parent class.

```python
class Animal:
    def eat(self):
        print("Eating")

class Dog(Animal):
    def bark(self):
        print("Bark")
```

### 8.2 Multiple inheritance
One subclass inherits from more than one parent class.

```python
class Father:
    def money(self):
        print("Father gives money")

class Mother:
    def caring(self):
        print("Mother is caring")

class Child(Father, Mother):
    def study(self):
        print("Child studies")
```

### 8.3 Multilevel inheritance
A class extends another class, which itself extends a third class.

```python
class Grandfather:
    def property(self):
        print("Family property")

class Father(Grandfather):
    def business(self):
        print("Family business")

class Son(Father):
    def job(self):
        print("Son's job")
```

### 8.4 Hierarchical inheritance
Multiple child classes inherit from the same parent class.

```python
class Vehicle:
    def start(self):
        print("Starting vehicle")

class Car(Vehicle):
    def airbags(self):
        print("Car airbags")

class Bike(Vehicle):
    def kick(self):
        print("Bike kick start")
```

### 8.5 Hybrid inheritance
A combination of inheritance patterns.

```python
class Grandfather:
    pass

class Father(Grandfather):
    pass

class Son(Father):
    pass

class Daughter(Father):
    pass

class Child(Son, Daughter):
    pass
```

### IS-A relationship
Inheritance represents an "IS-A" relationship: a derived class is a specialized version of its base class.

Examples:
- `Dog` IS-A `Animal`
- `Car` IS-A `Vehicle`
- `Developer` IS-A `Employee`
- `Student` IS-A `Person`

---

## 9. Polymorphism

Polymorphism allows the same interface to have different implementations.

### Method overriding
A subclass provides a new implementation for a method inherited from the parent class.

```python
class Animal:
    def sound(self):
        print("Animal sound")

class Dog(Animal):
    def sound(self):
        print("Bark")

Dog().sound()
```

### Polymorphic dispatch
Different classes implement the same method name.

```python
class Animal:
    def speak(self):
        raise NotImplementedError

class Dog(Animal):
    def speak(self):
        return "Woof!"

class Cat(Animal):
    def speak(self):
        return "Meow!"

for animal in (Dog(), Cat()):
    print(animal.speak())
```

### Operator overloading
Python operators behave differently depending on operand type.

```python
print(10 + 20)
print("Hello " + "World")
print([1, 2] + [3, 4])
```

### Overloading-like behavior
Python does not support traditional method overloading, but flexible argument lists provide similar behavior.

```python
class Calculator:
    def add(self, *args):
        return sum(args)

calculator = Calculator()
print(calculator.add(10, 20))
print(calculator.add(10, 20, 30))
```

---

## 10. Abstraction

Abstraction hides implementation details and exposes a simple interface.

### Definition
An abstract class defines required behavior while deferring the implementation to subclasses.

### Python support
- `abc.ABC`
- `@abstractmethod`

### Example

```python
from abc import ABC, abstractmethod

class Animal(ABC):
    @abstractmethod
    def make_sound(self):
        pass

    def sleep(self):
        print("Sleeping...")

class Dog(Animal):
    def make_sound(self):
        print("Woof!")

class Cat(Animal):
    def make_sound(self):
        print("Meow!")

Dog().make_sound()
Cat().make_sound()
Dog().sleep()
```

---

## 11. Exception Handling

Exception handling lets a program detect and respond to runtime errors while continuing execution gracefully.

### Structure
- `try`: code that may raise an exception
- `except`: handle a specific error
- `finally`: cleanup code that always runs

### Example

```python
try:
    num = int(input("Enter a number: "))
    result = 10 / num
    print(result)
except ZeroDivisionError:
    print("Cannot divide by zero!")
except ValueError:
    print("Please enter a valid number.")
finally:
    print("This always runs.")
```

### Common exceptions
- `ZeroDivisionError`
- `ValueError`
- `TypeError`
- `IndexError`
- `KeyError`
- `NameError`
- `FileNotFoundError`
- `ImportError`
- `AttributeError`
- `ModuleNotFoundError`

---

## 12. File Handling

File handling is the process of reading from and writing to files.

### Modes
- `r`: read only
- `w`: write only, overwrites existing file
- `a`: append only
- `r+`: read and write
- `w+`: write and read, overwrites existing file
- `a+`: append and read
- `x`: create new file, fails if file exists
- `rb`, `wb`: binary read/write

### Core functions
- `open(filename, mode)`
- `file.close()`
- `file.read()`
- `file.readline()`
- `file.readlines()`
- `file.write(data)`
- `file.writelines(lines)`

### Example: write and read

```python
with open("example.txt", "w") as file:
    file.write("Hello, World!\n")

with open("example.txt", "r") as file:
    content = file.read()
    print(content)
```

The `with` statement ensures the file is closed automatically.

---

## 13. JSON

JSON is a text-based format for structured data. Python uses the built-in `json` module to serialize and deserialize JSON.

### Example: write JSON

```python
import json

data = {"id": 1, "message": "Hello"}
with open("emp.json", "w") as file:
    json.dump(data, file)
```

### Example: read JSON

```python
import json

with open("emp.json", "r") as file:
    result = json.load(file)
    print(result)
```

### Example: string conversion

```python
import json

data = [30, 40, 50]
json_text = json.dumps(data)
print(json_text)
print(json.loads(json_text))
```

---

## 14. Copying Objects

### Shallow copy
A shallow copy creates a new object but shares nested references with the original.

```python
import copy

a = [[1, 2], [3, 4]]
b = copy.copy(a)
b[0][0] = 100
print(a)
print(b)
```

### Deep copy
A deep copy creates an independent copy of the object and all nested objects.

```python
import copy

a = [[1, 2], [3, 4]]
b = copy.deepcopy(a)
b[0][0] = 100
print(a)
print(b)
```

### Comparison
- Shallow copy copies the outer object and shares nested objects
- Deep copy duplicates nested objects recursively
- Shallow copy is faster and uses less memory
- Deep copy is safer when modifying nested structures

---

## 15. Advanced Concepts

### Decorators
A decorator is a callable that modifies or extends another callable without changing its source code.

```python
def decorator(func):
    def wrapper():
        print("Transaction initiated")
        func()
        print("Transaction completed")
    return wrapper

@decorator
def transaction():
    print("Executing all transaction steps.")

transaction()
```

### Iterators
An iterator provides sequential access to elements in a collection.

```python
mytuple = ("Apple", "Banana", "Cherry")
obj = iter(mytuple)
print(next(obj))
print(next(obj))
print(next(obj))
```

### Generators
Generators yield values lazily and save memory for large sequences.

```python
def numbers():
    yield 1
    yield 2
    yield 3

for value in numbers():
    print(value)
```

### Lambda functions
A lambda is a small anonymous function defined with `lambda`.

```python
square = lambda x: x * x
print(square(5))

add = lambda a, b: a + b
print(add(10, 20))
```

### `map`, `filter`, and `reduce`

```python
numbers = [1, 2, 3, 4]
print(list(map(lambda x: x * x, numbers)))
print(list(filter(lambda x: x % 2 == 0, numbers)))
```

```python
from functools import reduce
numbers = [1, 2, 3, 4]
result = reduce(lambda x, y: x + y, numbers)
print(result)
```

---

## 16. Concurrency

### Multithreading
Multithreading runs multiple threads within a single process. It is best suited for I/O-bound workloads.

```python
import threading
import time

def walk_dog(name):
    time.sleep(8)
    print(f"You finished walking {name}")

def take_out_trash():
    time.sleep(2)
    print("You took out the trash")

def get_mail():
    time.sleep(4)
    print("You got the mail")

chore1 = threading.Thread(target=walk_dog, args=("Scooby",))
chore2 = threading.Thread(target=take_out_trash)
chore3 = threading.Thread(target=get_mail)

chore1.start()
chore2.start()
chore3.start()

chore1.join()
chore2.join()
chore3.join()
print("All chores are complete!")
```

### Multiprocessing
Multiprocessing runs multiple processes in parallel and is suited for CPU-bound tasks.

```python
from multiprocessing import Process
import time

def square_numbers():
    for i in range(5):
        print(i * i)
        time.sleep(1)

if __name__ == "__main__":
    p1 = Process(target=square_numbers)
    p2 = Process(target=square_numbers)
    p1.start()
    p2.start()
    p1.join()
    p2.join()
    print("Process completed.")
```

### Global Interpreter Lock (GIL)
The GIL allows only one thread to execute Python bytecode at a time in CPython. It limits CPU-bound multithreaded programs but does not affect multiprocessing.

### Comparison
- Multithreading: uses threads, shared memory, efficient for I/O-bound operations
- Multiprocessing: uses processes, separate memory spaces, ideal for CPU-bound tasks
- Multithreading is limited by the GIL in CPython
- Multiprocessing bypasses the GIL by using separate interpreters

---

## 17. Summary

This document provides a strong foundation for Python developers. It combines object-oriented principles, error handling, file and data management, data copying, advanced language constructs, and concurrency models into a single professional reference.
