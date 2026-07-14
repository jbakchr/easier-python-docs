---
layout: default
title: Remove Whitespace
---

## Remove Whitespace

---

### Problem

I have a string with extra whitespace.

For example:

```text
   Hello world
```

or:

```text
Hello world
```

I want to remove the unwanted whitespace.

---

### Recommended Solution

Use `str.strip()`.

```python
text = "   Hello world   "

result = text.strip()

print(result)
```

Output:

```text
Hello world
```

---

### Why Use str.strip()?

`str.strip()` is built into Python.

It:

- Requires no imports
- Removes leading and trailing whitespace
- Is easy to read
- Works with spaces, tabs, and newlines

Most whitespace cleanup tasks can be solved with:

```python
text.strip()
```

---

### What Counts as Whitespace?

`strip()` removes common whitespace characters, including:

- Spaces
- Tabs (`\t`)
- Newlines (`\n`)

Example:

```python
text = "\n\tHello world\t\n"

result = text.strip()

print(result)
```

Output:

```text
Hello world
```

---

### Remove Whitespace from the Beginning Only

Use `str.lstrip()`.

```python
text = "   Hello world"

result = text.lstrip()

print(result)
```

Output:

```text
Hello world
```

---

### Remove Whitespace from the End Only

Use `str.rstrip()`.

```python
text = "Hello world   "

result = text.rstrip()

print(result)
```

Output:

```text
Hello world
```

---

### Working with User Input

A common use case is cleaning user input.

```python
name = input("Name: ").strip()

print(name)
```

This helps prevent accidental spaces from causing problems.

---

### Processing Lines from a File

```python
line = "Alice\n"

clean_line = line.strip()

print(clean_line)
```

Output:

```text
Alice
```

This is commonly used when reading text files.

---

### What Happens If There Is No Extra Whitespace?

Python returns a string with the same content.

```python
text = "Hello world"

result = text.strip()

print(result)
```

Output:

```text
Hello world
```

No error is raised.

---

### Removing Other Characters

`strip()` can also remove specific characters from the start and end of a string.

```python
text = "---Hello world---"

result = text.strip("-")

print(result)
```

Output:

```text
Hello world
```

---

### When Would I Use This?

Common situations include:

- Cleaning user input
- Processing text files
- Working with configuration files
- Cleaning CSV-style data
- Processing command-line arguments
- Formatting output

Example:

```python
email = "   alice@example.com   "

email = email.strip()

print(email)
```

Output:

```text
alice@example.com
```

---

### Related Problems

- Split a String
- Join Strings
- Replace Text
- Read a Text File
- Check if Text Contains a Substring

---

### Official Documentation

- str.strip()
- str.lstrip()
- str.rstrip()

Python Documentation:

- https://docs.python.org/3/library/stdtypes.html#str.strip

---

### Summary

If you need to remove whitespace from the beginning and end of a string, prefer:

```python
result = text.strip()
```

To remove whitespace only from the beginning:

```python
result = text.lstrip()
```

To remove whitespace only from the end:

```python
result = text.rstrip()
```

`str.strip()` is the standard Pythonic solution for removing unwanted whitespace from text.