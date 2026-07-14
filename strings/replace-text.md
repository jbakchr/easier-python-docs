---
layout: default
title: Replace Text
---

## Replace Text

---

### Problem

I have a string.

For example:

```text
Hello world
```

I want to replace part of the text with something else.

---

### Recommended Solution

Use `str.replace()`.

```python
text = "Hello world"

result = text.replace("world", "Python")

print(result)
```

Output:

```text
Hello Python
```

---

### Why Use str.replace()?

`str.replace()` is built into Python.

It:

- Is easy to read
- Requires no imports
- Replaces matching text directly
- Returns a new string

Most text replacement tasks can be solved with:

```python
text.replace(old, new)
```

---

### Replacing Multiple Occurrences

By default, Python replaces every matching occurrence.

```python
text = "red blue red green red"

result = text.replace("red", "yellow")

print(result)
```

Output:

```text
yellow blue yellow green yellow
```

---

### Replacing Spaces

A common use case is replacing spaces with another character.

```python
text = "hello world"

result = text.replace(" ", "-")

print(result)
```

Output:

```text
hello-world
```

This can be useful when generating filenames or URLs.

---

### Removing Text

Replace text with an empty string.

```python
text = "Hello world"

result = text.replace("world", "")

print(result)
```

Output:

```text
Hello
```

---

### Limiting the Number of Replacements

You can limit how many replacements Python performs.

```python
text = "red blue red green red"

result = text.replace("red", "yellow", 1)

print(result)
```

Output:

```text
yellow blue red green red
```

Only the first occurrence is replaced.

---

### What Happens if the Text Is Not Found?

Python returns the original string unchanged.

```python
text = "Hello world"

result = text.replace("Python", "Java")

print(result)
```

Output:

```text
Hello world
```

No error is raised.

---

### Replacing Text in User Input

```python
message = "I like Java"

message = message.replace("Java", "Python")

print(message)
```

Output:

```text
I like Python
```

---

### When Would I Use This?

Common situations include:

- Cleaning user input
- Formatting text
- Updating configuration values
- Generating URLs
- Modifying filenames
- Preparing text for output

Example:

```python
filename = "my report.txt"

safe_name = filename.replace(" ", "_")

print(safe_name)
```

Output:

```text
my_report.txt
```

---

### Related Problems

- Split a String
- Join Strings
- Remove Whitespace
- Check if Text Contains a Substring
- Check if Text Starts With a Value

---

### Official Documentation

- str.replace()

Python Documentation:

- https://docs.python.org/3/library/stdtypes.html#str.replace

---

### Summary

If you need to replace text in a string, prefer:

```python
result = text.replace("old", "new")
```

To remove text entirely:

```python
result = text.replace("old", "")
```

`str.replace()` is the standard Pythonic solution for replacing text in a string.