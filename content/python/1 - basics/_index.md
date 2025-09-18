+++
date = '2025-09-18T14:28:19+01:00'
title = 'Basics'
weight = 1
+++
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