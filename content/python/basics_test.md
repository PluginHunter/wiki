+++
date = '2025-09-18T14:23:35+01:00'
title = 'Basics - to remove'
weight = 3
+++


# Basics

## Basic Python functions
- `len()`  - function returns the length of a string, list, tuple, or dictionary.
- `type()` - function returns the type of a variable.

## Strings
### String slicing
- `string[start:end]` - slices a string from index `start` to `end`. The end index is exclusive.
- `string[start:end:step]` - slices a string from index `start` to `end` with a step of `step` (the step can have a negative value).

### String methods
- `string.lower()` - converts all characters in the string to lowercase.
- `string.upper()` - converts all characters in the string to uppercase.
- `string.capitalize()` - capitalizes the first character of the string.
- `string.title()` - capitalizes the first character of each word in the string.
- `string.strip()` - removes leading and trailing whitespace from the string.
  - `string.lstrip()` - removes leading whitespace from the string.
  - `string.rstrip()` - removes trailing whitespace from the string.
- `string.replace(old, new)` - replaces occurrences of `old` substring with `new` substring.
- `string.split(delimiter)` - splits the string into a list of substrings based on the specified `delimiter`.

### String functions
- `string.startswith(substring)` - checks if the string starts with the specified `substring`. Returns `True` or `False`.
- `string.endswith(substring)` - checks if the string ends with the specified `substring`. Returns `True` or `False`.
- `string.find(substring)` - returns the lowest index of the substring if found in the string. Returns `-1` if not found.
- `string.index(substring)` - returns the lowest index of the substring if found in the string. Raises a `ValueError` if not found.
- `string.count(substring)` - returns the number of occurrences of the substring in the string.

## Type casting
```python
float_num = 10.5
int_num = int(float_num)  # Converts float to int, truncating the decimal part
print(int_num)  # Output: 10
print(type(int_num))  # Output: <class 'int'>
str_num = str(int_num)  # Converts int to string
print(str_num)  # Output: '10'
print(type(str_num))  # Output: <class 'str'>
``` 

## Logical operators
- `and` or `&` - logical AND operator. Returns `True` if both operands are true.
- `or`  or `|`- logical OR operator. Returns `True` if at least one operand is true.
- `not` or `!` - logical NOT operator. Returns `True` if the operand is false.

## Conditional statements

```python
if a > b:
  print("a is greater than b")
elif a < b:
  print("a is less than b")
else:
  print("a is equal to b")
```

## Loops

### For loop
A for loop is used to iterate over a sequence (like a list, tuple, dictionary, set, or string - basically any iterable object).

```python
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
  print(fruit)
```
### While loop
A while loop is used to execute a block of code as long as a condition is true.
```python
i = 1
while i < 6:
  print(i)
  i += 1
```

# Data structures

## Lists - `"[ ]"`
A list is a **mutable** collection which is **ordered** and changeable. Allows duplicate members.
It can store items of different data types.
```python
fruits = ["apple", "banana", "cherry"]
print(fruits[0])  # First element: Output: apple
print(fruits[-1])  # Last element: Output: cherry

fruits.append("orange")  # Adds orange to the end of the list
print(fruits)  # Output: ['apple', 'banana', 'cherry', 'orange']

fruits.remove("banana")  # Removes banana from the list
print(fruits)  # Output: ['apple', 'cherry', 'orange']

fruits.insert(1, "kiwi")  # Inserts kiwi at index 1
print(fruits)  # Output: ['apple', 'kiwi', 'cherry', 'orange']

fruit[0]="mango"  # Changes the first element to mango
print(fruits)  # Output: ['mango', 'kiwi', 'cherry', 'orange']

popped = fruits.pop()  # Removes the last element (or you can specify an index)
                       # The removed element can be stored in a variable
print(fruits)  # Output: ['mango', 'kiwi', 'cherry']
print(popped)  # Output: orange

fruits.sort()  # Sorts the list in ascending order
print(fruits)  # Output: ['cherry', 'kiwi', 'mango']

fruits.reverse()  # Reverses the order of the list
print(fruits)  # Output: ['mango', 'kiwi', 'cherry']

fruits.append("kiwi")  # Adds another kiwi to the end of the list
print(fruits.count("kiwi"))  # Counts occurrences of kiwi: Output: 2

fruits.remove("kiwi")  # Removes the first occurrence of kiwi 
                       # (you can also use del fruits[1] to remove by index)
print(fruits)  # Output: ['mango', 'cherry', 'kiwi']

fruits.extend(["grape", "melon"])  # Adds multiple items to the end of the list
print(fruits)  # Output: ['mango', 'cherry', 'kiwi', 'grape', 'melon']
```
You can slice a list (or any other iterable) just like a string:
```python
fruits = ["apple", "banana", "cherry", "orange", "kiwi"]
print(fruits[1:3])  # Output: ['banana', 'cherry']
```

You can check if a value exists in a list using the `in` keyword:
```python
if "apple" in fruits:
  print("Apple is in the list")

## OR 

result = "apple" in fruits
print(result)  # Output: True

```
List unpacking - assigning list elements to variables
```python
fruits = ["apple", "banana", "cherry"]
x, y, z = fruits
print(x)  # Output: apple
print(y)  # Output: banana
print(z)  # Output: cherry

# If you have more variables than elements in the list, you will get a ValueError.
# To avoid this, you can use the * operator to assign the remaining elements to a list:
fruits = ["apple", "banana", "cherry", "orange", "kiwi"]
x, y, *z = fruits
print(x)  # Output: apple
print(y)  # Output: banana
print(z)  # Output: ['cherry', 'orange', 'kiwi']
```


## Tuples - `"( )"`
A tuple is an **immutable** collection which is **ordered** and unchangeable. Allows duplicate members.
It can store items of different data types.
```python
fruits = ("apple", "banana", "cherry")
print(fruits[0])  # First element: Output: apple
print(fruits[-1])  # Last element: Output: cherry
# fruits[0] = "mango"  # This will raise a TypeError because tuples are immutable
print(len(fruits))  # Output: 3
```

## Dictionaries - `"{ }"`
A dictionary is a **mutable** collection which is **unordered**, changeable, and indexed. No duplicate members.
It stores data in `key-value` pairs.
```python
person = {"name": "John", "age": 30, "city": "New York"}

print(person["name"])  # Output: John if exists, otherwise raises a KeyError
print(person.get("age"))  # Output: 30 if exists, otherwise None
print(person.get("job", "Not Found"))  # Output: Not Found if key doesn't exist

person["age"] = 31  # Updates the age
person["job"] = "Engineer"  # Adds a new key-value pair
print(person)  # Output: {'name': 'John', 'age': 31, 'city': 'New York', 'job': 'Engineer'}

del person["city"]  # Removes the key-value pair with key "city"
# OR
person.pop("city", None)  # Removes the key-value pair with key "city", returns None if key doesn't exist
person.popitem()  # Removes the last inserted key-value pair
print(person)  # Output: {'name': 'John', 'age': 31, 'job': 'Engineer'}
print(len(person))  # Output: 3

# Load/update multiple key-value pairs
person.update({"city": "New York", "country": "USA"})
print(person)  # Output: {'name': 'John', 'age': 31, 'job': 'Engineer', 'city': 'New York', 'country': 'USA'}
person.update(job="Manager")  # Updates the job
print(person)  # Output: {'name': 'John', 'age': 31, 'job': 'Manager', 'city': 'New York', 'country': 'USA'}
```

Iterating through a dictionary:
```python
person = {"name": "John", "age": 30, "city": "New York"}
# Iterate through keys
for key in person: 
    print(key, person[key])

# Iterate through values
for value in person.values(): 
    print(value)

# Iterate through key-value pairs
for key, value in person.items(): 
    print(key, value)
```

## Sets - `"{ }"`
A set is a **mutable** collection which is **unordered** and unindexed. No duplicate members.
It can store items of different data types. It's different from a dictionary because it only stores keys (no values).
```python
fruits = {"apple", "banana", "cherry"}
print(fruits)  # Output: {'banana', 'cherry', 'apple'} (order may vary)
print("banana" in fruits)  # Output: True if exists, otherwise False  
fruits.add("orange")  # Adds orange to the set
fruits.remove("banana")  # Removes banana from the set, raises KeyError if not found
fruits.discard("banana")  # Removes banana from the set if it exists, does nothing if not found
fruits.pop()  # Removes and returns an arbitrary element from the set
print(fruits)  # Output: {'cherry', 'apple', 'orange'}
print(len(fruits))  # Output: 3
```

Adding multiple items to a set (you need to provide an iterable like a list or another set):
```python
fruits = {"apple", "banana", "cherry"}
fruits.update(["orange", "kiwi"])  # Adds multiple items to the set 
fruits.update({"banana", "grape"})  # Adds multiple items to the set (duplicates are ignored)
print(fruits)  # Output: {'banana', 'cherry', 'orange', 'kiwi', 'apple', 'grape'}
``` 

# Functions
Basic function definition and usage:
```python
def greet(name):
  return f"Hello, {name}!"

print(greet("Alice"))  # Output: Hello, Alice!
```

A function with default parameters:
```python
def greet(name="Guest"):
  return f"Hello, {name}!"

print(greet())  # Output: Hello, Guest!
print(greet("Bob"))  # Output: Hello, Bob!

# If the function returns multiple values, they are returned as a tuple:
def get_coordinates():
  x = 10
  y = 20
  return x, y
```

Invoking a function with keyword arguments:
```python
def greet(name, age):
  return f"Hello, {name}! You are {age} years old."

print(greet(age=25, name="Charlie"))  # Output: Hello, Charlie! You are 25 years old.
```

Lambda function (anonymous function). It's useful for short, throwaway functions (when you don't want to formally define a function using `def`). Often used as callbacks or in functional programming (e.g., with `map()`, `filter()`, `reduce()`):
```python
# lambda arguments: expression(or logic)
add = lambda x, y: x + y
print(add(5, 3)) # Output: 8

def apply_operation(x, y, operation):
    return operation(x, y)
result = apply_operation(10, 5, lambda a, b: a * b)
print(result)  # Output: 50 
``` 

# Modules and Packages

You can import built-in modules, third-party modules (installed via pip), or your own custom modules.

```python
import math  # Importing a built-in module
print(math.sqrt(16))  # Output: 4.0 

import random as rnd  # Importing with an alias
print(rnd.randint(1, 10))  # Output: Random integer between 1 and 10  

from datetime import datetime  # Importing specific functions or classes from a module
now = datetime.now()
print(now)  # Output: Current date and time 

from datetime import datetime as dt  # Importing specific functions or classes with an alias
now = dt.now()
print(now)  # Output: Current date and time 

# Import custom module (make sure mymodule.py is in the same directory or in the Python path)
import mymodule
mymodule.greet("Alice")  # Assuming mymodule has a function greet()   
```

# Classes and Objects

Classes are blueprints for creating objects. An object is an instance of a class.

`self` represents the instance of the class. It is used to access variables and methods associated with the current object. If you don't use `self`, Python will not know which instance you are referring to (and most likely you will use a global variable or raise an error).

`__init__` is a special method (also called a constructor) that is automatically called when an object of the class is created. It is used to initialize the object's attributes.

```python
class Dog:
    # Class attribute
    species = "Canis familiaris"

    # Initializer / Instance attributes
    def __init__(self, name, age):
        self.name = name
        self.age = age

    # Instance method
    def bark(self):
        return f"{self.name} says woof!"
    def loud_bark(self):
        print(f"{self.name} says WOOF WOOF!")


pluto = Dog("Pluto", 3)

print(pluto.name)     # Output: Pluto
print(pluto.age)      # Output: 3
print(pluto.species)  # Output: Canis familiaris
print(pluto.bark())   # Output: Pluto says woof!
pluto.loud_bark()     # Output: Pluto says WOOF WOOF!
```

Duck typing - if it looks like a duck and quacks like a duck, it's a duck. It's usefull when you want to write functions that can work with different types of objects, as long as they have the same method or attribute.:
```python
class Duck:
    def make_sound(self):
        return "Quack!"
class Cat:
    def make_sound(self):
        return "Meow!"
class Dog:
    def make_sound(self):
        return "Woof!"

def animal_sound(animal):
    print(animal.make_sound())  # Works for any object that has a make_sound() method 

duck = Duck()
animal_sound(duck)  # Output: Quack!

dog = Dog()
animal_sound(dog)  # Output: Woof!

cat = Cat() 
animal_sound(cat)  # Output: Meow!
```

--- 
###### ToDo: 
- add functional programming examples (map, filter, reduce, lambda)
- add info about `*args` and `**kwargs`
- add info about `__init__` and classes
- add info about list comprehensions
- add info about importing modules and packages
- add asynchronous programming (async, await)
- add file handling (open, read, write, with)
- add table of contents
- add Best practices and coding standards (PEP 8) - pehaps another page?
- add info about annotations (type hints)
- add info about decorators
- add info about error and exception handling (try, except, finally, raise)
- make this a cheat sheet and publish on GitHub Pages
  - [guide1](https://www.curiousmints.com/deploying-a-hugo-website-to-github-pages-using-github-actions/)  
  - [guide2](https://www.testingwithmarie.com/posts/20241126-create-a-static-blog-with-hugo/)