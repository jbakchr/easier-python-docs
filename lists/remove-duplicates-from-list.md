---
layout: default
title: Remove Duplicates from a List
---

## Remove Duplicates from a List

---

### Problem

I have a list that contains duplicate values.

For example:

```python
["apple", "banana", "apple", "cherry", "banana"]
```

I want a list that contains each value only once.

---

### Recommended Solution

Use `set()`.

```python
fruits = [
    "apple",
    "banana",
    "apple",
    "cherry",
    "banana"
]

unique_fruits = list(set(fruits))

print(unique_fruits)
```

Output:

```python
['apple', 'banana', 'cherry']
```

---

### Why Use set()?

A set is a built-in Python data structure that stores unique values.

It:

- Automatically removes duplicates
- Is simple and concise
- Requires no imports
- Is part of the Python Standard Library

For many situations, removing duplicates is as simple as:

```python
unique_items = list(set(items))
```

---

### What Is a Set?

A set contains unique values.

Example:

```python
numbers = {1, 2, 3}
```

Unlike lists, sets cannot contain duplicate items.

```python
numbers = {1, 2, 2, 3}

print(numbers)
```

Output:

```python
{1, 2, 3}
```

Python automatically removes duplicates.

---

### Preserving the Original Order

One limitation of `set()` is that it does not preserve the original order.

```python
fruits = [
    "apple",
    "banana",
    "apple",
    "cherry"
]

unique_fruits = list(set(fruits))
```

The resulting order may differ from the original list.

If preserving order is important, use `dict.fromkeys()`.

```python
fruits = [
    "apple",
    "banana",
    "apple",
    "cherry"
]

unique_fruits = list(
    dict.fromkeys(fruits)
)

print(unique_fruits)
```

Output:

```python
['apple', 'banana', 'cherry']
```

This approach removes duplicates while keeping the original order.

---

### Removing Duplicate Numbers

```python
numbers = [1, 2, 2, 3, 3, 3]

unique_numbers = list(set(numbers))

print(unique_numbers)
```

Output:

```python
[1, 2, 3]
```

---

### Removing Duplicate Strings

```python
names = [
    "Alice",
    "Bob",
    "Alice",
    "Charlie"
]

unique_names = list(set(names))

print(unique_names)
```

Output:

```python
['Alice', 'Bob', 'Charlie']
```

---

### When Would I Use This?

Common situations include:

- Cleaning user input
- Processing CSV data
- Removing duplicate search results
- Working with API data
- Data analysis scripts
- Automation tasks

Example:

```python
tags = [
    "python",
    "json",
    "python",
    "pathlib"
]

unique_tags = list(set(tags))

print(unique_tags)
```

Output:

```python
['python', 'json', 'pathlib']
```

---

### Related Problems

- Add an Item to a List
- Remove an Item from a List
- Sort a List
- Filter a List
- Find an Item in a List

---

### Official Documentation

- set()
- dict.fromkeys()

Python Documentation:

- https://docs.python.org/3/library/stdtypes.html#set
- https://docs.python.org/3/library/stdtypes.html#dict.fromkeys

---

### Summary

If you simply need unique values, prefer:

```python
unique_items = list(set(items))
```

If you need to preserve the original order:

```python
unique_items = list(
    dict.fromkeys(items)
)
```

For most duplicate-removal tasks, `set()` is the standard Pythonic solution.