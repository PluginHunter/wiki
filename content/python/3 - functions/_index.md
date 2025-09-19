+++
date = '2025-09-19T08:23:57+01:00'
title = 'Functions'
weight = 3
+++
## Basics
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



## Modules and Packages

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

## Classes and Objects

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