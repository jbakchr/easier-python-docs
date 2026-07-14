---
layout: default
title: Join Strings
---

## Join Strings

---

### Problem

I have multiple strings.

For example:

```python
["apple", "banana", "cherry"]
```

I want to combine them into a single string.

---

### Recommended Solution

Use `str.join()`.

```python
items = ["apple", "banana", "cherry"]

result = ", ".join(items)

print(result)
```

Output:

```text
apple, banana, cherry
```

---

### Why Use str.join()?

`str.join()` is the standard Pythonic way to combine multiple strings.

It:

- Is built into Python
- Is easy to read
- Lets you choose a separator
- Works efficiently with large collections of strings

Most string-joining tasks can be solved with:

```python
separator.join(strings)
```

---

### Joining Without a Separator

Use an empty string if you want to combine strings directly.

```python
letters = ["P", "y", "t", "h", "o", "n"]

word = "".join(letters)

print(word)
```

Output:

```text
Python
```

---

### Joining With Spaces

A common use case is joining words into a sentence.

```python
words = ["Hello", "world"]

sentence = " ".join(words)

print(sentence)
```

Output:

```text
Hello world
```

---

### Joining Lines

You can join strings with newline characters.

```python
lines = ["Alice", "Bob", "Charlie"]

text = "\n".join(lines)

print(text)
```

Output:

```text
Alice
Bob
Charlie
```

This is useful when generating text files.

---

### Joining Path Components

Although `pathlib` is usually preferred for filesystem paths, joining strings can sometimes be useful.

```python
parts = ["api", "v1", "users"]

url = "/".join(parts)

print(url)
```

Output:

```text
api/v1/users
```

---

### What Happens With a Single Item?

Python simply returns the original string.

```python
items = ["hello"]

result = ", ".join(items)

print(result)
```

Output:

```text
hello
```

---

### When Would I Use This?

Common situations include:

- Building sentences
- Generating CSV-style text
- Creating URLs
- Formatting output
- Writing files
- Combining user input

Example:

```python
tags = ["python", "json", "pathlib"]

print(", ".join(tags))
```

Output:

```text
python, json, pathlib
```

---

### Related Problems

- Split a String
- Replace Text
- Remove Whitespace
- Read a Text File
- Write a Text File

---

### Official Documentation

- str.join()

Python Documentation:

- https://docs.python.org/3/library/stdtypes.html#str.join

---

### Summary

If you need to combine multiple strings into a single string, prefer:

```python
result = ", ".join(items)
```

If you want no separator:

```python
result = "".join(items)
```

`str.join()` is the standard Pythonic solution for combining strings.
