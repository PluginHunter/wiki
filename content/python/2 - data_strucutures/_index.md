+++
date = '2025-09-18T14:29:43+01:00'
title = 'Data_strucutures'
weight = 2
+++
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