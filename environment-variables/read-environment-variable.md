---
layout: default
title: Read an Environment Variable
---

## Read an Environment Variable

---

### Problem

I have an environment variable.

For example:

```text
DATABASE_URL=postgresql://localhost/mydb
```

I want to access its value from my Python program.

---

### Recommended Solution

Use `os.getenv()`.

```python
import os

database_url = os.getenv(
    "DATABASE_URL"
)

print(database_url)
```

Output:

```text
postgresql://localhost/mydb
```

---

### Why Use os.getenv()?

`os.getenv()` is part of Python's Standard Library.

It:

- Requires no external dependencies
- Reads environment variables by name
- Returns `None` if the variable does not exist
- Works on all major operating systems

For most situations, it is the recommended way to read environment variables.

---

### What Is an Environment Variable?

An environment variable is a value provided by the operating system.

Examples:

```text
DATABASE_URL
API_KEY
PORT
HOME
PATH
```

Programs often use environment variables for:

- Configuration
- Secrets
- File locations
- Runtime settings

---

### What Does os.getenv() Return?

`os.getenv()` returns the value of the environment variable as a string.

Example:

```python
import os

port = os.getenv("PORT")

print(port)
print(type(port))
```

Output:

```python
8080
<class 'str'>
```

Environment variables are always returned as strings.

---

### Reading a Common Environment Variable

```python
import os

home_directory = os.getenv(
    "HOME"
)

print(home_directory)
```

Output:

```text
/home/user
```

The exact value will vary depending on your system.

---

### What Happens if the Variable Does Not Exist?

`os.getenv()` returns `None`.

```python
import os

value = os.getenv(
    "DOES_NOT_EXIST"
)

print(value)
```

Output:

```python
None
```

No error is raised.

---

### Using os.environ

Another option is `os.environ`.

```python
import os

database_url = os.environ[
    "DATABASE_URL"
]

print(database_url)
```

Unlike `os.getenv()`, this raises an exception if the variable does not exist.

```text
KeyError
```

For most situations, `os.getenv()` is the simpler choice.

---

### Using Environment Variables for Configuration

A common use case is application configuration.

```python
import os

database_url = os.getenv(
    "DATABASE_URL"
)

debug = os.getenv("DEBUG")

print(database_url)
print(debug)
```

This allows configuration without changing your Python code.

---

### When Would I Use This?

Common situations include:

- Reading API keys
- Accessing database connection strings
- Configuring applications
- Command-line tools
- Automation scripts
- Containerized applications

Example:

```python
import os

api_key = os.getenv("API_KEY")

print(api_key)
```

---

### Related Problems

- Provide a Default Value
- Check Whether an Environment Variable Exists
- Read a JSON File
- Parse a Date String
- Read Command-Line Arguments

---

### Official Documentation

- os.getenv()
- os.environ

Python Documentation:

- https://docs.python.org/3/library/os.html#os.getenv
- https://docs.python.org/3/library/os.html#os.environ

---

### Summary

If you need to read an environment variable, prefer:

```python
import os

value = os.getenv(
    "VARIABLE_NAME"
)
```

This returns the value as a string.

If the variable does not exist, `os.getenv()` returns:

```python
None
```

For most Python applications, `os.getenv()` is the standard Pythonic solution for reading environment variables.