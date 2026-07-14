---
layout: default
title: Check if Text Starts with a Value
---

## Check if Text Starts with a Value

---

### Problem

I have some text.

For example:

```text
report-2026.txt
```

I want to know whether it starts with a specific value.

For example:

```text
report-
```

---

### Recommended Solution

Use `str.startswith()`.

```python
file_name = "report-2026.txt"

print(
    file_name.startswith("report-")
)
```

Output:

```python
True
```

---

### Why Use startswith()?

`startswith()` is built into Python.

It:

- Requires no imports
- Is easy to read
- Clearly expresses intent
- Returns a boolean value

For most situations, it is the recommended way to check whether text starts with a value.

---

### What Does startswith() Return?

`startswith()` returns:

```python
True
```

if the text starts with the specified value.

Otherwise it returns:

```python
False
```

Example:

```python
text = "hello world"

print(
    text.startswith("hello")
)
```

Output:

```python
True
```

---

### Checking a Prefix

```python
text = "report-2026.txt"

print(
    text.startswith("report-")
)
```

Output:

```python
True
```

---

### Checking a Value That Does Not Match

```python
text = "report-2026.txt"

print(
    text.startswith("image-")
)
```

Output:

```python
False
```

---

### Checking User Input

```python
command = "quit"

if command.startswith("q"):
    print("Exit command detected")
```

Output:

```text
Exit command detected
```

---

### Checking File Names

A common use case is filtering file names.

```python
file_name = "backup-2026.zip"

if file_name.startswith("backup-"):
    print("Backup file")
```

Output:

```text
Backup file
```

---

### Checking Multiple Possible Values

You can provide a tuple of prefixes.

```python
file_name = "report.csv"

print(
    file_name.startswith(
        ("report", "backup")
    )
)
```

Output:

```python
True
```

Python returns `True` if any of the values match.

---

### Case Sensitivity

`startswith()` is case-sensitive.

```python
text = "Hello"

print(
    text.startswith("hello")
)
```

Output:

```python
False
```

If case should not matter, convert the text first.

```python
text = "Hello"

print(
    text.lower().startswith(
        "hello"
    )
)
```

Output:

```python
True
```

---

### When Would I Use This?

Common situations include:

- Processing file names
- Validating user input
- Parsing simple commands
- Filtering text data
- Processing log files
- Automation scripts

Example:

```python
url = "https://example.com"

if url.startswith("https://"):
    print("Secure URL")
```

Output:

```text
Secure URL
```

---

### Related Problems

- Check if Text Ends with a Value
- Check if Text Contains a Substring
- Split a String
- Replace Text
- Remove Whitespace

---

### Official Documentation

- str.startswith()

Python Documentation:

- https://docs.python.org/3/library/stdtypes.html#str.startswith

---

### Summary

If you need to check whether text starts with a value, prefer:

```python
text.startswith("value")
```

This returns:

```python
True
```

when the text starts with the specified value and:

```python
False
```

otherwise.

For most Python applications, `startswith()` is the standard Pythonic solution for checking whether text begins with a specific value.