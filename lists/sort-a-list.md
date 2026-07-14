---
layout: default
title: Sort a List
---

## Sort a List

---

### Problem

I have a list.

For example:

```python
[3, 1, 4, 2]
```

I want to sort the items.

---

### Recommended Solution

Use `sorted()`.

```python
numbers = [3, 1, 4, 2]

result = sorted(numbers)

print(result)
```

Output:

```python
[1, 2, 3, 4]
```

---

### Why Use sorted()?

`sorted()` is built into Python.

It:

- Is easy to read
- Works with many data types
- Returns a new list
- Does not modify the original list

Most sorting tasks can be solved with:

```python
sorted(items)
```

---

### The Original List Is Not Changed

```python
numbers = [3, 1, 4, 2]

result = sorted(numbers)

print(numbers)
print(result)
```

Output:

```python
[3, 1, 4, 2]
[1, 2, 3, 4]
```

This is often useful when you want to preserve the original data.

---

### Sorting Strings

```python
names = ["Charlie", "Alice", "Bob"]

result = sorted(names)

print(result)
```

Output:

```python
['Alice', 'Bob', 'Charlie']
```

---

### Sorting in Reverse Order

Use `reverse=True`.

```python
numbers = [3, 1, 4, 2]

result = sorted(numbers, reverse=True)

print(result)
```

Output:

```python
[4, 3, 2, 1]
```

---

### Sorting by Length

Use the `key` parameter.

```python
words = ["banana", "kiwi", "apple"]

result = sorted(words, key=len)

print(result)
```

Output:

```python
['kiwi', 'apple', 'banana']
```

This is useful when sorting by a custom property.

---

### Sorting Dictionaries by a Value

```python
users = [
    {"name": "Alice", "age": 30},
    {"name": "Bob", "age": 25},
    {"name": "Charlie", "age": 35},
]

result = sorted(users, key=lambda user: user["age"])

print(result)
```

Output:

```python
[
    {'name': 'Bob', 'age': 25},
    {'name': 'Alice', 'age': 30},
    {'name': 'Charlie', 'age': 35}
]
```

---

### Using list.sort()

Python lists also provide a `sort()` method.

```python
numbers = [3, 1, 4, 2]

numbers.sort()

print(numbers)
```

Output:

```python
[1, 2, 3, 4]
```

Unlike `sorted()`, this modifies the original list.

---

### When Would I Use This?

Common situations include:

- Sorting filenames
- Sorting command results
- Sorting API responses
- Sorting users by name
- Sorting records by date
- Displaying data consistently

Example:

```python
files = [
    "report.txt",
    "notes.txt",
    "todo.txt",
]

for file in sorted(files):
    print(file)
```

Output:

```text
notes.txt
report.txt
todo.txt
```

---

### Related Problems

- Remove Duplicates from a List
- Find an Item in a List
- Filter a List
- List Files in a Directory
- Read JSON File

---

### Official Documentation

- sorted()
- list.sort()

Python Documentation:

- https://docs.python.org/3/library/functions.html#sorted
- https://docs.python.org/3/tutorial/datastructures.html

---

### Summary

If you need to sort a list, prefer:

```python
result = sorted(items)
```

For descending order:

```python
result = sorted(items, reverse=True)
```

To sort by a custom property:

```python
result = sorted(items, key=...)
```

`sorted()` is the standard Pythonic solution for sorting data.