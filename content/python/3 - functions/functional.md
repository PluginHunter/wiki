+++
date = '2025-09-18T14:28:19+01:00'
title = 'Functional programming'
+++

## Lambda Functions
Lambda functions (anonymous functions) are useful for short, throwaway functions (when you don't want to formally define a function using `def`). Often used as callbacks or in functional programming (e.g., with `map()`, `filter()`, `reduce()`):

```python
# lambda arguments: expression(or logic)
add = lambda x, y: x + y
print(add(5, 3)) # Output: 8

def apply_operation(x, y, operation):
    return operation(x, y)
result = apply_operation(10, 5, lambda a, b: a * b)
print(result)  # Output: 50 
``` 