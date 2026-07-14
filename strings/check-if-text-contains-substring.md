---
layout: default
title: Check if Text Contains a Substring
---

## Check if Text Contains a Substring

---

### Problem

I have a string.

For example:

```text
Hello world
```

I want to check whether it contains specific text.

---

### Recommended Solution

Use the `in` operator.

```python
text = "Hello world"

result = "world" in text

print(result)
```

Output:

```python
True
```

---

### Why Use the in Operator?

The `in` operator is the standard Pythonic way to check for text.

It:

- Is easy to read
- Requires no imports
- Returns `True` or `False`
- Works with any string

Most substring checks can be solved with:

```python
substring in text
```

---

### Checking for Missing Text

Use `not in` when you want to check that text is absent.

```python
text = "Hello world"

result = "Python" not in text

print(result)
```

Output:

```python
True
```

---

### Checking User Input

A common use case is validating input.

```python
email = "alice@example.com"

if "@" in email:
    print("Valid email format")
```

Output:

```text
Valid email format
```

---

### Checking File Extensions

```python
filename = "report.pdf"

if ".pdf" in filename:
    print("PDF file")
```

Output:

```text
PDF file
```

---

### The Check Is Case-Sensitive

By default, Python treats uppercase and lowercase letters differently.

```python
text = "Hello world"

print("hello" in text)
```

Output:

```python
False
```

---

### Case-Insensitive Checks

Convert both values to lowercase.

```python
text = "Hello world"

result = "hello".lower() in text.lower()

print(result)
```

Output:

```python
True
```

---

### What Happens If the Text Is Not Found?

Python returns `False`.

```python
text = "Hello world"

result = "Python" in text

print(result)
```

Output:

```python
False
```

No error is raised.

---

### Filtering Data

```python
message = "Error: Connection failed"

if "Error" in message:
    print("Something went wrong")
```

Output:

```text
Something went wrong
```

---

### When Would I Use This?

Common situations include:

- Validating user input
- Searching log messages
- Checking filenames
- Processing text files
- Filtering data
- Looking for keywords

Example:

```python
text = "Python is fun"

if "Python" in text:
    print("Found it")
```

Output:

```text
Found it
```

---

### Related Problems

- Check if Text Starts With a Value
- Check if Text Ends With a Value
- Split a String
- Replace Text
- Remove Whitespace

---

### Official Documentation

Python Documentation:

- https://docs.python.org/3/reference/expressions.html#membership-test-operations

---

### Summary

If you need to check whether text contains a substring, prefer:

```python
"world" in text
```

If you need to check that text is absent:

```python
"world" not in text
```

The `in` operator is the standard Pythonic solution for checking whether a string contains specific text.