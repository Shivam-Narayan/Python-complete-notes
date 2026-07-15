# Python Fundamentals and Object-Oriented Concepts

This document is a complete Python reference, organized for readability and practical use. It covers foundation-level topics, language features, object-oriented design, error handling, file operations, and concurrency.

---

## 1. What is Python?

Python is a high-level interpreted programming language that emphasizes readability and productivity.

- High-level: written in human-readable form.
- Interpreted: executed line by line by the Python interpreter.
- Dynamic: data types are determined at runtime.
- Cross-platform: runs on Windows, macOS, Linux, and other operating systems.

### Key features
- Simple syntax and fast learning curve.
- Large standard library and rich ecosystem.
- Portable and extensible.
- Supports multiple programming paradigms, including procedural, object-oriented, and functional styles.

---

## 2. Variables and Data Types

A variable stores a value and can change during execution.

### Common Python types
- `int` — integer numbers
- `float` — decimal numbers
- `str` — text
- `bool` — `True` or `False`

### Example

```python
count = 10
price = 99.95
name = "Shivam"
active = True
```

---

## 3. Operators

Operators perform calculations and comparisons.

### Arithmetic operators
- `+` addition
- `-` subtraction
- `*` multiplication
- `/` division (float result)
- `//` integer division
- `%` remainder
- `**` exponentiation

### Assignment operators
- `=` assign
- `+=` add and assign
- `-=` subtract and assign
- `*=` multiply and assign
- `/=` divide and assign
- `%=` modulus and assign
- `//=` floor divide and assign
- `**=` power and assign

### Comparison operators
- `==` equal to
- `!=` not equal to
- `<` less than
- `<=` less than or equal
- `>` greater than
- `>=` greater than or equal

### Logical operators
- `and` both conditions true
- `or` at least one condition true
- `not` negate condition

### Membership operators
- `in` checks whether a value is in a sequence
- `not in` checks whether a value is not in a sequence

### Identity operators
- `is` true when both operands refer to the same object
- `is not` true when operands are different objects

---

## 4. Core Collections

Python includes several built-in collection types.

### List
- Ordered, mutable, allows duplicates.
- Defined with square brackets.

```python
fruits = ["apple", "banana", "cherry"]
fruits.append("date")
```

### Tuple
- Ordered, immutable, allows duplicates.
- Defined with parentheses.

```python
point = (3, 4)
```

### Set
- Unordered, mutable, no duplicate elements.
- Defined with curly braces.

```python
colors = {"red", "green", "blue"}
```

### Dictionary
- Key-value pairs, keys must be unique.
- Defined with braces and colons.

```python
student = {"name": "Alice", "age": 20}
```

### Summary table

| Type | Mutable | Ordered | Duplicates | Syntax |
| --- | --- | --- | --- | --- |
| list | yes | yes | yes | `[ ]` |
| tuple | no | yes | yes | `( )` |
| set | yes | no | no | `{ }` |
| dict | yes | yes | keys unique | `{key: value}` |

---

## 5. Comprehensions

Comprehensions provide a compact way to create collections.

### List comprehension

```python
numbers = [1, 2, 3, 4]
squares = [x**2 for x in numbers]
```

### Set comprehension

```python
values = [1, 2, 2, 3]
unique_squares = {x**2 for x in values}
```

### Dictionary comprehension

```python
nums = [1, 2, 3, 4]
squares = {x: x**2 for x in nums}
```

---

## 6. Strings

Strings are sequences of characters and support many convenient operations.

### Quoting rules
- Single quotes: `'hello'`
- Double quotes: `"hello"`
- Triple quotes: `'''multi-line'''` or `"""multi-line"""`

### Common string methods
- `lower()`, `upper()`, `strip()`
- `split()`, `join()`
- `find()`, `replace()`
- `startswith()`, `endswith()`

### Example

```python
message = "Hello, World!"
print(message.lower())
print(message.replace("World", "Python"))
```

---

## 7. Conditional Statements

Use conditionals to run code only when certain conditions are met.

### if

```python
age = 20
if age >= 18:
    print("Adult")
```

### if-else

```python
age = 16
if age >= 18:
    print("Adult")
else:
    print("Minor")
```

### if-elif-else

```python
score = 75
if score >= 90:
    grade = "A"
elif score >= 75:
    grade = "B"
else:
    grade = "C"
print(grade)
```

### Ternary expression

```python
status = "Adult" if age >= 18 else "Minor"
```

---

## 8. Functions

A function is a reusable block of code that performs a specific task.

### Define and call

```python
def greet(name):
    return f"Hello, {name}!"

message = greet("Alice")
print(message)
```

### Built-in functions
- `print()`
- `len()`
- `type()`
- `input()`
- `int()`, `float()`, `str()`
- `range()`
- `sum()`
- `min()`, `max()`
- `sorted()`
- `list()`, `tuple()`, `dict()`, `set()`
- `abs()`
- `round()`
- `enumerate()`
- `zip()`
- `any()`, `all()`
- `help()`

### Aliasing functions

```python
def greet(name):
    print(f"Hello {name}")

say_hello = greet
say_hello("Alice")
```

### String formatting

```python
name = "Alice"
age = 30
print("My name is {} and I am {} years old.".format(name, age))
print(f"My name is {name} and I am {age} years old.")
```

---

## 9. Object-Oriented Programming (OOP)

OOP organizes code around objects and data.

### Class
A class defines the attributes and methods for a category of objects.

```python
class Car:
    pass
```

### Object
An object is an instance of a class.

```python
car = Car()
```

### self
`self` refers to the current object inside instance methods.

```python
class Person:
    def __init__(self, name):
        self.name = name
```

### Constructor (`__init__`)
The constructor initializes object state.

```python
class Car:
    def __init__(self, brand):
        self.brand = brand
```

### `__str__`
This method defines a readable string representation.

```python
class Car:
    def __init__(self, brand, model):
        self.brand = brand
        self.model = model

    def __str__(self):
        return f"{self.brand} {self.model}"
```

---

## 10. Encapsulation in OOP

Encapsulation hides implementation details by using private attributes and public methods.

```python
class Employee:
    def __init__(self):
        self.__salary = 0

    def set_salary(self, salary):
        self.__salary = salary

    def get_salary(self):
        return self.__salary
```

### Rationale
- Keeps object state consistent
- Prevents accidental modification
- Makes validation easier

---

## 11. Inheritance

Inheritance allows a class to reuse code from another class.

```python
class Animal:
    def sound(self):
        print("Animal makes a sound")

class Dog(Animal):
    pass
```

### Inherited members
A subclass inherits attributes and methods from its parent.

```python
class Developer(Employee):
    pass
```

### Benefits
- Reuse code
- Reduce duplication
- Organize related types

---

## 12. Inheritance Types

### Single inheritance
A subclass inherits from one parent.

### Multiple inheritance
A subclass inherits from multiple parents.

### Multilevel inheritance
A subclass derives from a class that already inherits from another.

### Hierarchical inheritance
Multiple subclasses inherit from the same parent.

### Hybrid inheritance
A combination of different inheritance models.

---

## 13. Polymorphism

Polymorphism means the same interface can have different implementations.

### Method overriding

```python
class Animal:
    def sound(self):
        print("Animal sound")

class Dog(Animal):
    def sound(self):
        print("Bark")
```

### Example of polymorphic behavior

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

### Overloading-like behavior
Use flexible arguments instead of traditional overloading.

```python
class Calculator:
    def add(self, *args):
        return sum(args)
```

---

## 14. Abstraction

Abstraction exposes only what is necessary and hides complexity.

```python
from abc import ABC, abstractmethod

class Animal(ABC):
    @abstractmethod
    def make_sound(self):
        pass

    def sleep(self):
        print("Sleeping...")
```

---

## 15. Exception Handling

Use exceptions to handle runtime errors gracefully.

### Structure
- `try` block contains code that may fail.
- `except` block handles specific errors.
- `finally` block runs no matter what.

### Example

```python
try:
    num = int(input("Enter a number: "))
    print(10 / num)
except ZeroDivisionError:
    print("Cannot divide by zero.")
except ValueError:
    print("Please type a valid number.")
finally:
    print("Done.")
```

---

## 16. File Handling

File operations let Python read and write persistent data.

### Common modes
- `r` read
- `w` write
- `a` append
- `r+` read/write
- `x` create only

### Example

```python
with open("example.txt", "w") as file:
    file.write("Hello\n")

with open("example.txt", "r") as file:
    print(file.read())
```

---

## 17. JSON

JSON is a text format for structured data.

### Example write

```python
import json

data = {"id": 1, "message": "Hello"}
with open("emp.json", "w") as file:
    json.dump(data, file)
```

### Example read

```python
import json
with open("emp.json", "r") as file:
    result = json.load(file)
    print(result)
```

---

## 18. Copying Objects

### Shallow copy
Shares nested references with the original object.

```python
import copy

a = [[1, 2], [3, 4]]
b = copy.copy(a)
```

### Deep copy
Creates an independent nested copy.

```python
import copy

b = copy.deepcopy(a)
```

---

## 19. Advanced Python Concepts

### Decorators
Decorators wrap a function with additional behavior.

```python
def tracer(func):
    def wrapper(*args, **kwargs):
        print("Starting function")
        result = func(*args, **kwargs)
        print("Finished function")
        return result
    return wrapper

@tracer
def example():
    print("Running")

example()
```

### Iterators
An iterator iterates over a sequence one item at a time.

```python
tuple_data = ("Apple", "Banana")
iterator = iter(tuple_data)
print(next(iterator))
print(next(iterator))
```

### Generators
Generators yield values lazily.

```python
def count_up():
    n = 1
    while n <= 3:
        yield n
        n += 1
```

### Lambda functions
Anonymous functions created with `lambda`.

```python
square = lambda x: x * x
print(square(5))
```

### Built-ins: `map`, `filter`, `reduce`

```python
numbers = [1, 2, 3, 4]
print(list(map(lambda x: x * x, numbers)))
print(list(filter(lambda x: x % 2 == 0, numbers)))
```

```python
from functools import reduce
product = reduce(lambda x, y: x * y, numbers)
print(product)
```

---

## 20. Concurrency

### Multithreading
Threads share memory and are useful for I/O-bound work.

```python
import threading
import time

def task(name, delay):
    time.sleep(delay)
    print(name)

threads = [
    threading.Thread(target=task, args=("A", 1)),
    threading.Thread(target=task, args=("B", 2)),
]
for t in threads:
    t.start()
for t in threads:
    t.join()
```

### Multiprocessing
Processes run in separate memory spaces and work well for CPU-bound work.

```python
from multiprocessing import Process
import time

def worker():
    time.sleep(1)
    print("Done")

if __name__ == "__main__":
    p = Process(target=worker)
    p.start()
    p.join()
```

### Global Interpreter Lock (GIL)
The GIL allows only one thread to execute Python bytecode at a time in CPython, which affects CPU-bound threading.

---

## 21. Useful Concepts

### `if __name__ == "__main__"`
This check ensures code only runs when the file is executed directly.

```python
if __name__ == "__main__":
    print("Running as script")
```

### Performance tips
- Choose appropriate data structures.
- Use built-ins and standard library tools.
- Limit unnecessary copies.
- Apply lazy evaluation where possible.

---

## 22. Conclusion

This reference provides a practical overview of Python fundamentals, object-oriented design, core libraries, and concurrency. It is intended to support learning and quick review.
