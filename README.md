# Python Programming Concepts

This repository provides an overview of fundamental Python programming concepts, including data types, control structures, functions, object-oriented programming, file handling, and more.

## Table of Contents

1. [Introduction to Python](#introduction-to-python)
2. [Variables and Data Types](#variables-and-data-types)
3. [Operators](#operators)
4. [Special Data Types](#special-data-types)
5. [Control Structures](#control-structures)
6. [Functions](#functions)
7. [Object-Oriented Programming (OOP)](#object-oriented-programming-oop)
8. [File Handling](#file-handling)
9. [Advanced Concepts](#advanced-concepts)

---

## Introduction to Python

- **Python** is a high-level, interpreted programming language.
- **Features**:
  - Simple and easy to learn.
  - Cross-platform and platform-independent.
  - Extensible and dynamically typed.
  - Free and downloadable.

---

## Variables and Data Types

### Variables
- Used to store data or information.
- Examples:
  - Integer: `x = 10`
  - Float: `x = 10.00`
  - String: `name = 'shivam'`

### Data Types
- Specify the type of data.
- Common types:
  - `int`
  - `float`
  - `bool` (Boolean: `True/False`)
  - `str` (String)

---

## Operators

1. **Arithmetic Operators**: `+, -, *, %, /, //`
2. **Assignment Operators**: `=, +=, -=, *=, %=, /=, //=`
3. **Relational Operators**: `==, !=, <, <=, >, >=`
4. **Logical Operators**: `and, or, not`
5. **Membership Operators**: `in, not in`
6. **Identity Operators**: `is, is not`

---

## Special Data Types

### List
- Ordered, mutable collection.
- Supports indexing, slicing, and duplicate values.

### Tuple
- Ordered, immutable collection.
- Supports indexing, slicing, and duplicate values.

### Set
- Unordered, mutable collection.
- Does not allow duplicate values.

### Dictionary
- Ordered, mutable collection of key-value pairs.
- Keys must be unique.

---

## Control Structures

- **if Statement**
- **if-else Statement**
- **if-elif-else Chain**
- **Nested if Statements**
- **Ternary Operator**: `status = "Adult" if age >= 18 else "Minor"`

---

## Functions

### User-Defined Functions
- Defined using the `def` keyword.
- Example:
  ```python
  def greet(name):
      return f"Hello, {name}!"

## Table of Contents

1. [Built-in Functions](#built-in-functions)
2. [Function Aliasing](#function-aliasing)
3. [Object-Oriented Programming (OOP)](#object-oriented-programming-oop)
4. [File Handling](#file-handling)
5. [Advanced Concepts](#advanced-concepts)
6. [License](#license)

---

## Built-in Functions

Python comes with several built-in functions that are always available. Some commonly used ones include:

- `print()`: Outputs data to the console.
- `len()`: Returns the number of items in an object.
- `type()`: Returns the type of an object.
- `input()`: Takes input from the user.
- `range()`: Generates a sequence of numbers.

---

## Function Aliasing

Assigning another name to a function is called **function aliasing**. This allows you to use different names for the same function.


def fun(name):
    print(f"Hello {name}")

cheer = fun  # Assigning 'fun' to 'cheer'
cheer("Alice")  # Output: Hello Alice


## Table of Contents

1. [Object-Oriented Programming (OOP)](#object-oriented-programming-oop)
2. [File Handling](#file-handling)
3. [Advanced Concepts](#advanced-concepts)
4. [License](#license)

---

## Object-Oriented Programming (OOP)

### Classes and Objects

- **Class**: A blueprint for creating objects.
- **Object**: An instance of a class.

### Key Concepts

- **Encapsulation**: Binding data and methods into a single unit (class).
- **Inheritance**: Reusability of code. A class can inherit the attributes and methods of another class.
- **Polymorphism**: Different forms of methods. Methods in a class can behave differently based on the object.
- **Abstraction**: Hiding the internal implementation details and exposing only the necessary features.

#### Example:

class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def greet(self):
        return f"Hello, my name is {self.name} and I am {self.age} years old."

# Python Programming Concepts

This repository provides an overview of file handling, advanced Python concepts, and special functions, including decorators, iterators, generators, and functional programming techniques.

## Table of Contents

1. [File Handling](#file-handling)
2. [Advanced Concepts](#advanced-concepts)
   - [Decorators](#decorators)
   - [Iterators and Generators](#iterators-and-generators)
   - [Special Functions](#special-functions)
3. [License](#license)

---

## File Handling

### Modes:

- `'r'`: Read
- `'w'`: Write
- `'a'`: Append
- `'x'`: Create

### Common Methods:

- `open()`: Opens a file.
- `read()`: Reads the content of a file.
- `write()`: Writes to a file.
- `close()`: Closes a file after operations.

#### Example:
```python
with open("example.txt", "r") as file:
    content = file.read()
    print(content)

