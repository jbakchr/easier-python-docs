---
layout: default
title: Check if Text Ends with a Value
---

## Check if Text Ends with a Value

---

### Problem

I have some text.

For example:

```text
report.pdf
```

I want to know whether it ends with a specific value.

For example:

```text
.pdf
```

---

### Recommended Solution

Use `str.endswith()`.

```python
file_name = "report.pdf"

print(
    file_name.endswith(".pdf")
)
```

Output:

```python
True
```

---

### Why Use endswith()?

`endswith()` is built into Python.

It:

- Requires no imports
- Is easy to read
- Clearly expresses intent
- Returns a boolean value

For most situations, it is the recommended way to check whether text ends with a value.

---

### What Does endswith() Return?

`endswith()` returns:

```python
True
```

if the text ends with the specified value.

Otherwise it returns:

```python
False
```

Example:

```python
text = "report.pdf"

print(
    text.endswith(".pdf")
)
```

Output:

```python
True
```

---

### Checking a File Extension

A common use case is checking file extensions.

```python
file_name = "report.pdf"

if file_name.endswith(".pdf"):
    print("PDF file")
```

Output:

```text
PDF file
```

---

### Checking a Value That Does Not Match

```python
file_name = "report.pdf"

print(
    file_name.endswith(".txt")
)
```

Output:

```python
False
```

---

### Checking URLs

```python
url = "https://example.com"

print(
    url.endswith(".com")
)
```

Output:

```python
True
```

---

### Checking Multiple Possible Values

You can provide multiple values using a tuple.

```python
file_name = "report.csv"

print(
    file_name.endswith(
        (".csv", ".json")
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

`endswith()` is case-sensitive.

```python
file_name = "REPORT.PDF"

print(
    file_name.endswith(".pdf")
)
```

Output:

```python
False
```

If case should not matter, convert the text first.

```python
file_name = "REPORT.PDF"

print(
    file_name.lower().endswith(
        ".pdf"
    )
)
```

Output:

```python
True
```

---

### Filtering File Names

A common use case is filtering files by extension.

```python
files = [
    "report.pdf",
    "notes.txt",
    "data.csv"
]

for file_name in files:
    if file_name.endswith(".csv"):
        print(file_name)
```

Output:

```text
data.csv
```

---

### When Would I Use This?

Common situations include:

- Checking file extensions
- Filtering files
- Validating URLs
- Processing user input
- Working with exported data
- Automation scripts

Example:

```python
file_name = "backup.zip"

if file_name.endswith(".zip"):
    print("ZIP archive")
```

Output:

```text
ZIP archive
```

---

### Related Problems

- Check if Text Starts with a Value
- Check if Text Contains a Substring
- Split a String
- Get File Extension
- List Files in a Directory

---

### Official Documentation

- str.endswith()

Python Documentation:

- https://docs.python.org/3/library/stdtypes.html#str.endswith

---

### Summary

If you need to check whether text ends with a value, prefer:

```python
text.endswith("value")
```

This returns:

```python
True
```

when the text ends with the specified value and:

```python
False
```

otherwise.

For most Python applications, `endswith()` is the standard Pythonic solution for checking whether text ends with a specific value.