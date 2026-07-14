---
layout: default
title: Provide a Default Value
---

## Provide a Default Value

---

### Problem

I want to read an environment variable.

For example:

```text
PORT
```

If the variable does not exist, I want to use a default value.

For example:

```text
8080
```

---

### Recommended Solution

Use `os.getenv()` with a default value.

```python
import os

port = os.getenv(
    "PORT",
    "8080"
)

print(port)
```

Output:

```text
8080
```

If the environment variable exists, its value is returned.

Otherwise, the default value is used.

---

### Why Use os.getenv()?

`os.getenv()` is part of Python's Standard Library.

It:

- Requires no external dependencies
- Reads environment variables by name
- Supports fallback values
- Avoids errors when variables are missing

For most situations, it is the recommended way to provide default values.

---

### How Does the Default Value Work?

The second argument is the fallback value.

```python
import os

value = os.getenv(
    "VARIABLE_NAME",
    "default-value"
)
```

Python returns:

- The environment variable if it exists
- The default value if it does not

---

### Reading a Port Number

A common use case is application configuration.

```python
import os

port = os.getenv(
    "PORT",
    "8080"
)

print(port)
```

Output:

```text
8080
```

Applications often use a default port during development.

---

### Reading a Database URL

```python
import os

database_url = os.getenv(
    "DATABASE_URL",
    "sqlite:///app.db"
)

print(database_url)
```

If `DATABASE_URL` is not set, the application uses the local database.

---

### What Happens if the Variable Exists?

Suppose:

```text
PORT=5000
```

Then:

```python
import os

port = os.getenv(
    "PORT",
    "8080"
)

print(port)
```

Output:

```text
5000
```

The environment variable takes precedence over the default value.

---

### Environment Variables Are Strings

Environment variables are always returned as strings.

```python
import os

port = os.getenv(
    "PORT",
    "8080"
)

print(type(port))
```

Output:

```python
<class 'str'>
```

If a numeric value is required, convert it explicitly.

```python
import os

port = int(
    os.getenv(
        "PORT",
        "8080"
    )
)

print(port)
```

Output:

```text
8080
```

---

### Using a Default for Debug Settings

Another common example:

```python
import os

debug = os.getenv(
    "DEBUG",
    "false"
)

print(debug)
```

Output:

```text
false
```

---

### When Would I Use This?

Common situations include:

- Application configuration
- Database connection settings
- API keys
- Port numbers
- Feature flags
- Automation scripts

Example:

```python
import os

log_level = os.getenv(
    "LOG_LEVEL",
    "INFO"
)

print(log_level)
```

---

### Related Problems

- Read an Environment Variable
- Check Whether an Environment Variable Exists
- Read a JSON File
- Parse a Date String
- Read Command-Line Arguments

---

### Official Documentation

- os.getenv()

Python Documentation:

- https://docs.python.org/3/library/os.html#os.getenv

---

### Summary

If you need a fallback value when reading an environment variable, prefer:

```python
import os

value = os.getenv(
    "VARIABLE_NAME",
    "default-value"
)
```

If the environment variable exists, Python returns its value.

Otherwise, Python returns the default value.

For most Python applications, `os.getenv()` is the standard Pythonic solution for providing default configuration values.