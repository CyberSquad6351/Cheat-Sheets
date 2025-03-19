# Python 3 Comprehensive Cheat Sheet

## Table of Contents
1. [Basic Syntax](#basic-syntax)
2. [Data Types](#data-types)
3. [Variables and Operators](#variables-and-operators)
4. [Control Flow](#control-flow)
5. [Functions](#functions)
6. [Data Structures](#data-structures)
7. [File Operations](#file-operations)
8. [Exception Handling](#exception-handling)
9. [Modules and Packages](#modules-and-packages)
10. [Object-Oriented Programming](#object-oriented-programming)
11. [Standard Library Highlights](#standard-library-highlights)

## Basic Syntax

### Comments
```python
# Single line comment

'''
Multi-line comment
(actually a string literal not assigned to a variable)
'''

"""
Another multi-line comment
(using double quotes)
"""
```

### Printing and Input
```python
print("Hello, World!")  # Basic print
print("Multiple", "arguments", sep="-")  # Custom separator
print("No newline", end=" ")  # Custom end character

name = input("Enter your name: ")  # Get user input
```

### Indentation
```python
# Python uses indentation (typically 4 spaces) to define code blocks
if True:
    print("Indented code block")
    if True:
        print("Nested indentation")
```

## Data Types

### Numeric Types
```python
x = 10          # int
y = 3.14        # float
z = 1 + 2j      # complex
```

### Boolean
```python
is_valid = True   # Boolean true
is_invalid = False  # Boolean false
```

### Strings
```python
name = "Python"    # String with double quotes
language = 'Python'  # String with single quotes

# Multi-line strings
description = """Python is a 
programming language"""

# String operations
print(name[0])      # Indexing: P
print(name[1:3])    # Slicing: yt
print(name * 2)     # Repetition: PythonPython
print(name + " 3")  # Concatenation: Python 3
print(f"{name} 3")  # f-string (formatted string): Python 3
print("{} {}".format(name, 3))  # String formatting: Python 3
```

### None Type
```python
x = None  # Represents absence of value
```

## Variables and Operators

### Variable Assignment
```python
x = 5           # Basic assignment
x, y = 5, 10    # Multiple assignment
x, y = y, x     # Swap values
```

### Arithmetic Operators
```python
a = 10
b = 3

print(a + b)    # Addition: 13
print(a - b)    # Subtraction: 7
print(a * b)    # Multiplication: 30
print(a / b)    # Division: 3.333... (returns float)
print(a // b)   # Floor division: 3 (returns int)
print(a % b)    # Modulus: 1
print(a ** b)   # Exponentiation: 1000
```

### Comparison Operators
```python
print(a == b)   # Equal to: False
print(a != b)   # Not equal to: True
print(a > b)    # Greater than: True
print(a < b)    # Less than: False
print(a >= b)   # Greater than or equal to: True
print(a <= b)   # Less than or equal to: False
```

### Logical Operators
```python
print(True and False)  # Logical AND: False
print(True or False)   # Logical OR: True
print(not True)        # Logical NOT: False
```

### Assignment Operators
```python
x = 10
x += 5    # Same as: x = x + 5
x -= 5    # Same as: x = x - 5
x *= 2    # Same as: x = x * 2
x /= 2    # Same as: x = x / 2
x //= 2   # Same as: x = x // 2
x %= 2    # Same as: x = x % 2
x **= 2   # Same as: x = x ** 2
```

### Identity Operators
```python
x = ["apple"]
y = ["apple"]
z = x

print(x is z)      # True (same object)
print(x is y)      # False (different objects)
print(x is not y)  # True
```

### Membership Operators
```python
fruits = ["apple", "banana"]
print("apple" in fruits)        # True
print("orange" not in fruits)   # True
```

## Control Flow

### Conditional Statements
```python
x = 10

# If statement
if x > 5:
    print("x is greater than 5")

# If-else statement
if x > 15:
    print("x is greater than 15")
else:
    print("x is not greater than 15")

# If-elif-else statement
if x > 15:
    print("x is greater than 15")
elif x > 5:
    print("x is greater than 5 but not greater than 15")
else:
    print("x is not greater than 5")

# Ternary operator (conditional expression)
result = "Even" if x % 2 == 0 else "Odd"
```

### Loops

#### While Loop
```python
count = 0
while count < 5:
    print(count)
    count += 1
```

#### For Loop
```python
# Iterate over a sequence
for fruit in ["apple", "banana", "cherry"]:
    print(fruit)

# Iterate over a range
for i in range(5):    # 0 to 4
    print(i)

for i in range(2, 5):  # 2 to 4
    print(i)

for i in range(0, 10, 2):  # 0, 2, 4, 6, 8
    print(i)
```

#### Loop Control
```python
# Break statement
for i in range(10):
    if i == 5:
        break  # Exit the loop
    print(i)

# Continue statement
for i in range(10):
    if i % 2 == 0:
        continue  # Skip the rest of the loop body
    print(i)  # Print only odd numbers

# Else clause (executes when loop completes normally)
for i in range(5):
    print(i)
else:
    print("Loop completed")
```

## Functions

### Defining and Calling Functions
```python
# Basic function
def greet():
    print("Hello, World!")

greet()  # Call the function

# Function with parameters
def greet_person(name):
    print(f"Hello, {name}!")

greet_person("Alice")  # Hello, Alice!

# Function with return value
def add(a, b):
    return a + b

result = add(3, 5)  # result = 8
```

### Default and Keyword Arguments
```python
# Default parameters
def greet(name="Guest"):
    print(f"Hello, {name}!")

greet()          # Hello, Guest!
greet("Alice")   # Hello, Alice!

# Keyword arguments
def describe_person(name, age, occupation):
    print(f"{name} is {age} years old and works as a {occupation}.")

describe_person(name="Alice", age=30, occupation="Engineer")
describe_person(age=25, occupation="Doctor", name="Bob")  # Order doesn't matter
```

### Variable-length Arguments
```python
# *args (tuple of positional arguments)
def add_all(*numbers):
    return sum(numbers)

print(add_all(1, 2, 3, 4))  # 10

# **kwargs (dictionary of keyword arguments)
def person_info(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")

person_info(name="Alice", age=30, city="New York")
```

### Lambda Functions
```python
# Anonymous functions
square = lambda x: x ** 2
print(square(5))  # 25

# Used with built-in functions
numbers = [1, 2, 3, 4, 5]
squared = list(map(lambda x: x ** 2, numbers))  # [1, 4, 9, 16, 25]
evens = list(filter(lambda x: x % 2 == a, numbers))  # [2, 4]
```

## Data Structures

### Lists
```python
# Creating lists
fruits = ["apple", "banana", "cherry"]
numbers = [1, 2, 3, 4, 5]
mixed = [1, "hello", 3.14, True]
nested = [1, [2, 3], 4]

# Accessing elements
print(fruits[0])       # First element: apple
print(fruits[-1])      # Last element: cherry
print(fruits[1:3])     # Slicing: ['banana', 'cherry']

# List operations
fruits.append("orange")        # Add element to end
fruits.insert(1, "blueberry")  # Insert at position
fruits.remove("banana")        # Remove by value
popped = fruits.pop()          # Remove and return last element
fruits.pop(0)                  # Remove and return element at index
fruits.sort()                  # Sort in place
fruits.reverse()               # Reverse in place
print(len(fruits))             # Length of list
print("apple" in fruits)       # Check membership

# List comprehensions
squares = [x**2 for x in range(10)]
evens = [x for x in range(10) if x % 2 == 0]
```

### Tuples
```python
# Creating tuples (immutable lists)
coordinates = (10, 20)
person = ("Alice", 30, "Engineer")
single_item = (1,)  # Comma is necessary for single item

# Accessing elements (same as lists)
print(coordinates[0])  # 10
print(coordinates[1])  # 20

# Tuple operations
print(len(coordinates))  # 2
print(10 in coordinates)  # True

# Tuple unpacking
name, age, occupation = person
x, y = coordinates
```

### Dictionaries
```python
# Creating dictionaries (key-value pairs)
person = {
    "name": "Alice",
    "age": 30,
    "occupation": "Engineer"
}

# Accessing elements
print(person["name"])           # Alice
print(person.get("age"))        # 30
print(person.get("salary", 0))  # 0 (default if key not found)

# Dictionary operations
person["city"] = "New York"     # Add or update key-value pair
popped = person.pop("age")      # Remove and return value
print("name" in person)         # Check if key exists
print(len(person))              # Number of key-value pairs

# Dictionary methods
print(person.keys())       # View of all keys
print(person.values())     # View of all values
print(person.items())      # View of all (key, value) pairs

# Dictionary comprehension
squares = {x: x**2 for x in range(5)}  # {0: 0, 1: 1, 2: 4, 3: 9, 4: 16}
```

### Sets
```python
# Creating sets (unordered collections of unique elements)
fruits = {"apple", "banana", "cherry"}
numbers = {1, 2, 3, 4, 5}

# Set operations
fruits.add("orange")            # Add element
fruits.remove("banana")         # Remove element (raises error if not found)
fruits.discard("grapes")        # Remove if exists (doesn't raise error)
print(len(fruits))              # Number of elements
print("apple" in fruits)        # Check membership

# Set operations
a = {1, 2, 3, 4}
b = {3, 4, 5, 6}
print(a | b)  # Union: {1, 2, 3, 4, 5, 6}
print(a & b)  # Intersection: {3, 4}
print(a - b)  # Difference: {1, 2}
print(a ^ b)  # Symmetric difference: {1, 2, 5, 6}

# Set comprehension
even_squares = {x**2 for x in range(10) if x % 2 == 0}
```

## File Operations

### Reading Files
```python
# Reading an entire file
with open("file.txt", "r") as file:
    content = file.read()  # Read entire file as string

# Reading line by line
with open("file.txt", "r") as file:
    for line in file:
        print(line.strip())  # Strip removes trailing newlines

# Reading all lines into a list
with open("file.txt", "r") as file:
    lines = file.readlines()  # List of all lines
```

### Writing Files
```python
# Writing to a file (overwrites existing content)
with open("output.txt", "w") as file:
    file.write("Hello, World!")
    file.write("Another line\n")

# Appending to a file
with open("output.txt", "a") as file:
    file.write("Appended text\n")
```

### Working with CSV Files
```python
import csv

# Reading CSV
with open("data.csv", "r") as file:
    reader = csv.reader(file)
    for row in reader:
        print(row)  # List of values

# Writing CSV
with open("output.csv", "w", newline="") as file:
    writer = csv.writer(file)
    writer.writerow(["Name", "Age"])
    writer.writerow(["Alice", 30])
```

### Working with JSON Files
```python
import json

# Reading JSON
with open("data.json", "r") as file:
    data = json.load(file)  # Parse JSON into Python object

# Writing JSON
data = {"name": "Alice", "age": 30}
with open("output.json", "w") as file:
    json.dump(data, file, indent=4)  # Write Python object as JSON
```

## Exception Handling

### Basic Exception Handling
```python
try:
    x = 10 / 0  # This will raise a ZeroDivisionError
except ZeroDivisionError:
    print("Cannot divide by zero")
```

### Multiple Exception Types
```python
try:
    num = int(input("Enter a number: "))
    result = 10 / num
except ValueError:
    print("Invalid input, not a number")
except ZeroDivisionError:
    print("Cannot divide by zero")
```

### Else and Finally Clauses
```python
try:
    num = int(input("Enter a number: "))
    result = 10 / num
except ValueError:
    print("Invalid input, not a number")
except ZeroDivisionError:
    print("Cannot divide by zero")
else:
    print(f"Result: {result}")  # Executes if no exception occurred
finally:
    print("Execution completed")  # Always executes
```

### Raising Exceptions
```python
def validate_age(age):
    if age < 0:
        raise ValueError("Age cannot be negative")
    if age > 120:
        raise ValueError("Age is too high")
    return age

try:
    validate_age(-5)
except ValueError as error:
    print(error)  # Age cannot be negative
```

### Custom Exceptions
```python
class CustomError(Exception):
    def __init__(self, message):
        self.message = message
        super().__init__(self.message)

try:
    raise CustomError("This is a custom error")
except CustomError as error:
    print(error)
```

## Modules and Packages

### Importing Modules
```python
import math  # Import the entire math module
print(math.sqrt(16))  # 4.0

from math import sqrt  # Import specific function
print(sqrt(16))  # 4.0

from math import sqrt as square_root  # Import with alias
print(square_root(16))  # 4.0

import math as m  # Import module with alias
print(m.sqrt(16))  # 4.0

from math import *  # Import all functions (not recommended)
print(sqrt(16))  # 4.0
```

### Creating Modules
```python
# File: mymodule.py
def greet(name):
    return f"Hello, {name}!"

PI = 3.14159

# In another file
import mymodule
print(mymodule.greet("Alice"))  # Hello, Alice!
print(mymodule.PI)  # 3.14159
```

### Package Structure
```
my_package/
│
├── __init__.py
├── module1.py
└── module2.py
```

```python
# Using packages
import my_package.module1
from my_package import module2
from my_package.module1 import function1
```

## Object-Oriented Programming

### Classes and Objects
```python
class Person:
    # Class variable (shared among all instances)
    species = "Homo Sapiens"
    
    # Constructor
    def __init__(self, name, age):
        # Instance variables (unique to each instance)
        self.name = name
        self.age = age
    
    # Instance method
    def greet(self):
        return f"Hello, my name is {self.name}"
    
    # Class method
    @classmethod
    def create_anonymous(cls):
        return cls("Anonymous", 0)
    
    # Static method
    @staticmethod
    def is_adult(age):
        return age >= 18

# Creating objects
person1 = Person("Alice", 30)
person2 = Person("Bob", 25)

# Accessing attributes and methods
print(person1.name)  # Alice
print(person1.greet())  # Hello, my name is Alice
print(Person.species)  # Homo Sapiens

# Using class and static methods
anonymous = Person.create_anonymous()
print(Person.is_adult(20))  # True
```

### Inheritance
```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    
    def greet(self):
        return f"Hello, my name is {self.name}"

class Student(Person):
    def __init__(self, name, age, student_id):
        super().__init__(name, age)  # Call parent constructor
        self.student_id = student_id
    
    def study(self):
        return f"{self.name} is studying"
    
    # Method overriding
    def greet(self):
        return f"{super().greet()} and I'm a student"

# Creating a Student object
student = Student("Alice", 20, "A12345")
print(student.greet())  # Hello, my name is Alice and I'm a student
print(student.study())  # Alice is studying
```

### Encapsulation
```python
class BankAccount:
    def __init__(self, owner, balance=0):
        self.owner = owner
        self.__balance = balance  # Private attribute (name mangling)
    
    def deposit(self, amount):
        if amount > 0:
            self.__balance += amount
            return True
        return False
    
    def withdraw(self, amount):
        if 0 < amount <= self.__balance:
            self.__balance -= amount
            return True
        return False
    
    def get_balance(self):
        return self.__balance

account = BankAccount("Alice", 1000)
print(account.get_balance())  # 1000
account.deposit(500)
print(account.get_balance())  # 1500
```

### Polymorphism
```python
class Animal:
    def make_sound(self):
        pass

class Dog(Animal):
    def make_sound(self):
        return "Woof!"

class Cat(Animal):
    def make_sound(self):
        return "Meow!"

def animal_sound(animal):
    return animal.make_sound()

dog = Dog()
cat = Cat()
print(animal_sound(dog))  # Woof!
print(animal_sound(cat))  # Meow!
```

## Standard Library Highlights

### Math Operations
```python
import math

print(math.sqrt(16))       # Square root: 4.0
print(math.pow(2, 3))      # Power: 8.0
print(math.ceil(4.2))      # Ceiling: 5
print(math.floor(4.8))     # Floor: 4
print(math.sin(math.pi/2)) # Sine: 1.0
```

### Random Numbers
```python
import random

print(random.random())            # Random float between 0 and 1
print(random.randint(1, 10))      # Random integer between 1 and 10
print(random.choice([1, 2, 3, 4])) # Random item from list
random.shuffle([1, 2, 3, 4])      # Shuffle list in place
```

### Date and Time
```python
import datetime

# Current date and time
now = datetime.datetime.now()
print(now)  # 2023-05-20 15:30:45.123456

# Creating date objects
date = datetime.date(2023, 5, 20)
time = datetime.time(15, 30, 45)
dt = datetime.datetime(2023, 5, 20, 15, 30, 45)

# Date formatting
print(now.strftime("%Y-%m-%d %H:%M:%S"))  # 2023-05-20 15:30:45

# Date arithmetic
tomorrow = datetime.date.today() + datetime.timedelta(days=1)
```

### Regular Expressions
```python
import re

text = "The quick brown fox"
pattern = r"quick"

# Search for pattern
match = re.search(pattern, text)
if match:
    print(f"Found '{match.group()}' at position {match.start()}")

# Find all occurrences
matches = re.findall(r"\w+", text)  # ['The', 'quick', 'brown', 'fox']

# Replace
new_text = re.sub(r"quick", "slow", text)  # The slow brown fox
```

### Collections
```python
from collections import Counter, defaultdict, namedtuple

# Counter: count occurrences
colors = ["red", "blue", "red", "green", "blue", "red"]
color_count = Counter(colors)
print(color_count)  # Counter({'red': 3, 'blue': 2, 'green': 1})

# defaultdict: dictionary with default values
fruit_count = defaultdict(int)  # Default value is 0
for fruit in ["apple", "banana", "apple"]:
    fruit_count[fruit] += 1
print(fruit_count)  # defaultdict(<class 'int'>, {'apple': 2, 'banana': 1})

# namedtuple: tuple with named fields
Person = namedtuple("Person", ["name", "age"])
alice = Person("Alice", 30)
print(alice.name)  # Alice
print(alice.age)   # 30
```

### OS Operations
```python
import os

# Current working directory
print(os.getcwd())

# List directory contents
print(os.listdir())

# Create directory
os.mkdir("new_directory")

# Remove file
os.remove("file.txt")

# Check if path exists
print(os.path.exists("file.txt"))

# Join paths (platform independent)
path = os.path.join("directory", "file.txt")
```

### JSON Processing
```python
import json

# Convert Python object to JSON string
data = {"name": "Alice", "age": 30}
json_str = json.dumps(data, indent=4)
print(json_str)

# Parse JSON string to Python object
parsed_data = json.loads(json_str)
print(parsed_data["name"])  # Alice
```

This cheat sheet provides a comprehensive overview of Python 3's core features and common libraries. Use it as a quick reference for syntax and functionality as you develop your Python applications.
