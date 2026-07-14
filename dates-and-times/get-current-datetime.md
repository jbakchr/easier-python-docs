---
layout: default
title: Get Current Datetime
---

## Get Current Datetime

---

### Problem

I need the current date and time in my Python program.

For example:

```text
2026-07-14 09:42:15
```

---

### Recommended Solution

Use `datetime.now()` from the `datetime` module.

```python
from datetime import datetime

now = datetime.now()

print(now)
```

Output:

```text
2026-07-14 09:42:15.123456
```

---

### Why Use datetime.now()?

`datetime.now()` is part of Python's Standard Library.

It:

- Requires no external dependencies
- Returns the current local date and time
- Produces a `datetime` object
- Is simple and easy to read

For most situations, it is the recommended way to get the current date and time.

---

### What Does datetime.now() Return?

`datetime.now()` returns a `datetime` object.

```python
from datetime import datetime

now = datetime.now()

print(type(now))
```

Output:

```python
<class 'datetime.datetime'>
```

A `datetime` object contains:

- Year
- Month
- Day
- Hour
- Minute
- Second
- Microsecond

Example:

```python
from datetime import datetime

now = datetime.now()

print(now.year)
print(now.month)
print(now.day)

print(now.hour)
print(now.minute)
print(now.second)
```

---

### Converting a Datetime to a String

Datetimes are often displayed as text.

```python
from datetime import datetime

now = datetime.now()

print(str(now))
```

Output:

```text
2026-07-14 09:42:15.123456
```

---

### Formatting the Datetime

Use `strftime()` to create a custom format.

```python
from datetime import datetime

now = datetime.now()

formatted = now.strftime(
    "%Y-%m-%d %H:%M:%S"
)

print(formatted)
```

Output:

```text
2026-07-14 09:42:15
```

Another example:

```python
formatted = now.strftime(
    "%d-%m-%Y %H:%M"
)

print(formatted)
```

Output:

```text
14-07-2026 09:42
```

---

### Current Datetime vs Current Date

A datetime contains both a date and a time.

```text
Year
Month
Day
Hour
Minute
Second
```

Example:

```python
from datetime import datetime

now = datetime.now()

print(now)
```

Output:

```text
2026-07-14 09:42:15.123456
```

If you only need the date, prefer:

```python
from datetime import date

today = date.today()
```

Output:

```text
2026-07-14
```

---

### Using the Current Datetime in a File Name

A common use case is creating timestamped files.

```python
from datetime import datetime

timestamp = datetime.now().strftime(
    "%Y%m%d-%H%M%S"
)

file_name = f"backup-{timestamp}.txt"

print(file_name)
```

Output:

```text
backup-20260714-094215.txt
```

---

### When Would I Use This?

Common situations include:

- Logging events
- Creating backups
- Timestamping files
- Automation scripts
- Command-line tools
- Recording when data was created

Example:

```python
from datetime import datetime

print(
    f"Started at: {datetime.now()}"
)
```

---

### Related Problems

- Get Current Date
- Format a Date
- Parse a Date String
- Write a Text File
- Append to a Text File

---

### Official Documentation

- datetime.datetime
- datetime.now()
- datetime.strftime()

Python Documentation:

- https://docs.python.org/3/library/datetime.html

---

### Summary

If you need the current date and time, prefer:

```python
from datetime import datetime

now = datetime.now()
```

This returns a `datetime` object representing the current local date and time.

For most Python applications, `datetime.now()` is the standard Pythonic solution.