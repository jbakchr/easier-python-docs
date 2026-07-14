---
layout: default
title: Split a String
---

## Split a String

---

### Problem

I have a string.

For example:

```text
apple,banana,cherry
```

I want to split it into individual values.

---

### Recommended Solution

Use `str.split()`.

```python
text = "apple,banana,cherry"

items = text.split(",")

print(items)
```

Output:

```python
['apple', 'banana', 'cherry']
```

---

### Why Use str.split()?

`str.split()` is built into Python.

It:

- Is simple and easy to read
- Works for many common text-processing tasks
- Requires no imports
- Returns a Python list

Most string splitting tasks can be solved with:

```python
text.split(separator)
```

---

### What Does split() Return?

`split()` returns a list of strings.

Example:

```python
text = "red,green,blue"

colors = text.split(",")

print(colors)
```

Output:

```python
['red', 'green', 'blue']
```

Each item becomes an element in the list.

---

### Splitting by Spaces

If you do not provide a separator, Python splits on whitespace.

```python
text = "Alice Bob Charlie"

names = text.split()

print(names)
```

Output:

```python
['Alice', 'Bob', 'Charlie']
```

This is useful for processing user input and simple text data.

---

### Splitting Lines

A common use case is processing text line by line.

```python
text = """Alice
Bob
Charlie"""

lines = text.split("\n")

print(lines)
```

Output:

```python
['Alice', 'Bob', 'Charlie']
```

---

### Limiting the Number of Splits

You can limit how many times Python splits the string.

```python
text = "name:Alice:developer"

parts = text.split(":", 1)

print(parts)
```

Output:

```python
['name', 'Alice:developer']
```

This is useful when only the first separator matters.

---

### What Happens if the Separator Is Not Found?

Python returns a list containing the original string.

```python
text = "hello"

result = text.split(",")

print(result)
```

Output:

```python
['hello']
```

No error is raised.

---

### Splitting a CSV-Style String

```python
text = "apple,banana,cherry"

items = text.split(",")

for item in items:
    print(item)
```

Output:

```text
apple
banana
cherry
```

---

### When Would I Use This?

Common situations include:

- Processing user input
- Reading configuration values
- Parsing simple CSV-style data
- Working with log files
- Processing command-line arguments
- Breaking text into words

Example:

```python
tags = "python,json,pathlib"

for tag in tags.split(","):
    print(tag)
```

---

### Related Problems

- Join Strings
- Replace Text
- Remove Whitespace
- Check if Text Contains a Substring
- Read a Text File

---

### Official Documentation

- str.split()

Python Documentation:

- https://docs.python.org/3/library/stdtypes.html#str.split

---

### Summary

If you need to split text into smaller pieces, prefer:

```python
items = text.split(",")
```

If you want to split on whitespace:

```python
words = text.split()
```

`str.split()` is the standard Pythonic solution for dividing text into a list of values.