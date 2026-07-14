---
layout: default
title: Parse a Date String
---

## Parse a Date String

---

### Problem

I have a date stored as text.

For example:

```text
2026-07-14
```

I want to convert it into a Python date object.

---

### Recommended Solution

Use `datetime.strptime()`.

```python
from datetime import datetime

date_string = "2026-07-14"

date_value = datetime.strptime(
    date_string,
    "%Y-%m-%d"
)

print(date_value)
```

Output:

```text
2026-07-14 00:00:00
```

---

### Why Use strptime()?

`strptime()` is part of Python's Standard Library.

It:

- Converts text into date or datetime objects
- Supports many date formats
- Requires no external dependencies
- Makes date values easier to work with

For most situations, it is the recommended way to parse date strings.

---

### What Does strptime() Return?

`strptime()` returns a `datetime` object.

```python
from datetime import datetime

date_value = datetime.strptime(
    "2026-07-14",
    "%Y-%m-%d"
)

print(type(date_value))
```

Output:

```python
<class 'datetime.datetime'>
```

This allows you to access:

- Year
- Month
- Day
- Hour
- Minute
- Second

Example:

```python
from datetime import datetime

date_value = datetime.strptime(
    "2026-07-14",
    "%Y-%m-%d"
)

print(date_value.year)
print(date_value.month)
print(date_value.day)
```

Output:

```text
2026
7
14
```

---

### Understanding the Format String

The second argument tells Python how the date is formatted.

```python
"%Y-%m-%d"
```

Meaning:

<table>
<tr>
<th>Code</th>
<th>Meaning</th>
</tr>
<tr>
<td>%Y</td>
<td>Year (4 digits)</td>
</tr>
<tr>
<td>%m</td>
<td>Month</td>
</tr>
<tr>
<td>%d</td>
<td>Day</td>
</tr>
</table>

Python uses this format to determine how to interpret the text.

---

### Parsing a Different Date Format

Suppose the date is:

```text
14/07/2026
```

Use a matching format string:

```python
from datetime import datetime

date_value = datetime.strptime(
    "14/07/2026",
    "%d/%m/%Y"
)

print(date_value)
```

Output:

```text
2026-07-14 00:00:00
```

---

### Converting to a date Object

If you only need the date portion, convert the result to a `date`.

```python
from datetime import datetime

date_value = datetime.strptime(
    "2026-07-14",
    "%Y-%m-%d"
).date()

print(date_value)
```

Output:

```text
2026-07-14
```

---

### Parsing a Datetime String

`strptime()` can also parse dates that include a time.

```python
from datetime import datetime

timestamp = datetime.strptime(
    "2026-07-14 10:30:45",
    "%Y-%m-%d %H:%M:%S"
)

print(timestamp)
```

Output:

```text
2026-07-14 10:30:45
```

---

### What Happens if the Format Does Not Match?

Python raises a `ValueError`.

```python
from datetime import datetime

datetime.strptime(
    "14-07-2026",
    "%Y-%m-%d"
)
```

Error:

```text
ValueError
```

The format string must match the text exactly.

---

### When Would I Use This?

Common situations include:

- Reading dates from files
- Processing CSV data
- Working with API responses
- Reading user input
- Automation scripts
- Data analysis

Example:

```python
from datetime import datetime

date_string = "2026-07-14"

date_value = datetime.strptime(
    date_string,
    "%Y-%m-%d"
)

print(date_value.year)
```

---

### Related Problems

- [Get Current Date](dates-and-times/get-current-date)
- Get Current Datetime
- Format a Date
- Read a CSV File
- Read a JSON File

---

### Official Documentation

- datetime.strptime()
- datetime.datetime

Python Documentation:

- https://docs.python.org/3/library/datetime.html#strftime-and-strptime-format-codes

---

### Summary

If you need to convert a date string into a Python date or datetime object, prefer:

```python
from datetime import datetime

date_value = datetime.strptime(
    date_string,
    "%Y-%m-%d"
)
```

If you only need the date portion:

```python
date_value = datetime.strptime(
    date_string,
    "%Y-%m-%d"
).date()
```

For most Python applications, `datetime.strptime()` is the standard Pythonic solution for parsing date strings.