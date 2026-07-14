---
layout: default
title: Get Current Date
---

## Get Current Date

---

### Problem

I need today's date in my Python program.

For example:

```text
2026-07-14
```

---

### Recommended Solution

Use `date.today()` from the `datetime` module.

```python
from datetime import date

today = date.today()

print(today)
```

Output:

```text
2026-07-14
```

---

### Why Use date.today()?

`date.today()` is part of Python's Standard Library.

It:

- Requires no external dependencies
- Returns the current local date
- Produces a `date` object
- Is simple and easy to read

For most situations, it is the recommended way to get today's date.

---

### What Does date.today() Return?

`date.today()` returns a `date` object.

```python
from datetime import date

today = date.today()

print(type(today))
```

Output:

```python
<class 'datetime.date'>
```

A `date` object contains:

- Year
- Month
- Day

Example:

```python
from datetime import date

today = date.today()

print(today.year)
print(today.month)
print(today.day)
```

Output:

```text
2026
7
14
```

---

### Converting the Date to a String

Dates are often displayed as text.

```python
from datetime import date

today = date.today()

print(str(today))
```

Output:

```text
2026-07-14
```

Python uses the ISO format:

```text
YYYY-MM-DD
```

---

### Formatting the Date

Use `strftime()` to create a custom format.

```python
from datetime import date

today = date.today()

formatted = today.strftime(
    "%d-%m-%Y"
)

print(formatted)
```

Output:

```text
14-07-2026
```

Another example:

```python
formatted = today.strftime(
    "%B %d, %Y"
)

print(formatted)
```

Output:

```text
July 14, 2026
```

---

### Current Date vs Current Datetime

A date contains only:

```text
Year
Month
Day
```

A datetime also contains:

```text
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
2026-07-14 09:30:15.123456
```

If you only need the date, prefer:

```python
from datetime import date

today = date.today()
```

---

### Using Today in a File Name

A common use case is creating dated files.

```python
from datetime import date

file_name = (
    f"report-{date.today()}.txt"
)

print(file_name)
```

Output:

```text
report-2026-07-14.txt
```

---

### When Would I Use This?

Common situations include:

- Creating reports
- Logging events
- Generating file names
- Automation scripts
- Command-line tools
- Recording when data was created

Example:

```python
from datetime import date

print(
    f"Backup created: {date.today()}"
)
```

---

### Related Problems

- Get Current Datetime
- Format a Date
- Parse a Date String
- Read an Environment Variable
- Write a Text File

---

### Official Documentation

- datetime.date
- date.today()
- date.strftime()

Python Documentation:

- https://docs.python.org/3/library/datetime.html

---

### Summary

If you need today's date, prefer:

```python
from datetime import date

today = date.today()
```

This returns a `date` object representing the current local date.

For most Python applications, `date.today()` is the standard Pythonic solution.