---
layout: default
title: Check Whether an Environment Variable Exists
---

## Check Whether an Environment Variable Exists

---

### Problem

I want to check whether an environment variable is defined.

For example:

```text
DATABASE_URL
```

If the variable exists, I want to use it.

If it does not exist, I may want to take a different action.

---

### Recommended Solution

Use `os.getenv()` and check whether the result is `None`.

```python
import os

database_url = os.getenv(
    "DATABASE_URL"
)

if database_url is not None:
    print("Variable exists")
else:
    print("Variable does not exist")
```

---

### Why Use os.getenv()?

`os.getenv()` is part of Python's Standard Library.

It:

- Requires no external dependencies
- Returns the variable's value if it exists
- Returns `None` if it does not exist
- Works on all major operating systems

For most situations, it is the recommended way to check whether an environment variable exists.

---

### Checking Whether a Variable Exists

```python
import os

if os.getenv("DATABASE_URL") is not None:
    print("Variable exists")
else:
    print("Variable does not exist")
```

Output:

```text
Variable exists
```

or

```text
Variable does not exist
```

depending on your environment.

---

### What Does os.getenv() Return?

If the variable exists:

```python
import os

value = os.getenv("DATABASE_URL")

print(value)
```

Output:

```text
postgresql://localhost/mydb
```

If the variable does not exist:

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

---

### Using os.environ

You can also check `os.environ` directly.

```python
import os

if "DATABASE_URL" in os.environ:
    print("Variable exists")
```

This works because `os.environ` behaves like a dictionary.

---

### Which Approach Should I Use?

For most situations, prefer:

```python
os.getenv("VARIABLE_NAME")
```

because you often want the value immediately after checking whether it exists.

Example:

```python
import os

api_key = os.getenv("API_KEY")

if api_key is not None:
    print(api_key)
```

---

### Checking Multiple Variables

A common use case is validating application configuration.

```python
import os

required_variables = [
    "DATABASE_URL",
    "API_KEY"
]

for name in required_variables:
    if os.getenv(name) is None:
        print(
            f"Missing variable: {name}"
        )
```

---

### When Would I Use This?

Common situations include:

- Validating application configuration
- Checking API keys
- Verifying database settings
- Command-line tools
- Automation scripts
- Containerized applications

Example:

```python
import os

if os.getenv("API_KEY") is None:
    print(
        "Please set API_KEY"
    )
```

---

### Related Problems

- Read an Environment Variable
- Provide a Default Value
- Read a JSON File
- Read Command-Line Arguments
- Parse a Date String

---

### Official Documentation

- os.getenv()
- os.environ

Python Documentation:

- https://docs.python.org/3/library/os.html#os.getenv
- https://docs.python.org/3/library/os.html#os.environ

---

### Summary

If you need to check whether an environment variable exists, prefer:

```python
import os

if os.getenv("VARIABLE_NAME") is not None:
    print("Variable exists")
```

If the variable exists, `os.getenv()` returns its value.

If it does not exist, `os.getenv()` returns:

```python
None
```

For most Python applications, this is the standard Pythonic way to check whether an environment variable exists.