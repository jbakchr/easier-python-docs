---
layout: default
title: Format a Date
---

## Format a Date

---

### Problem

I have a date.

For example:

```python
from datetime import date

today = date(2026, 7, 14)
```

I want to display it in a specific format.

For example:

```text
14-07-2026
```

or

```text
July 14, 2026
```

---

### Recommended Solution

Use `strftime()`.

```python
from datetime import date

today = date(2026, 7, 14)

formatted = today.strftime(
    "%d-%m-%Y"
)

print(formatted)
```

Output:

```text
14-07-2026
```

---

### Why Use strftime()?

`strftime()` is part of Python's Standard Library.

It:

- Works with both `date` and `datetime` objects
- Supports many common date formats
- Requires no external dependencies
- Produces human-readable strings

For most situations, it is the recommended way to format dates.

---

### Formatting a Date

```python
from datetime import date

today = date(2026, 7, 14)

formatted = today.strftime(
    "%d-%m-%Y"
)

print(formatted)
```

Output:

```text
14-07-2026
```

---

### Common Format Codes

<table>
<tr>
<th>Code</th>
<th>Meaning</th>
<th>Example</th>
</tr>
<tr>
<td>%Y</td>
<td>Year (4 digits)</td>
<td>2026</td>
</tr>
<tr>
<td>%m</td>
<td>Month</td>
<td>07</td>
</tr>
<tr>
<td>%d</td>
<td>Day</td>
<td>14</td>
</tr>
<tr>
<td>%H</td>
<td>Hour (24-hour clock)</td>
<td>09</td>
</tr>
<tr>
<td>%M</td>
<td>Minute</td>
<td>42</td>
</tr>
<tr>
<td>%S</td>
<td>Second</td>
<td>15</td>
</tr>
<tr>
<td>%B</td>
<td>Full month name</td>
<td>July</td>
</tr>
</table>

---

### ISO Date Format

A common format is:

```text
YYYY-MM-DD
```

Example:

```python
from datetime import date

today = date(2026, 7, 14)

print(
    today.strftime("%Y-%m-%d")
)
```

Output:

```text
2026-07-14
```

This format is widely used in APIs, databases, and configuration files.

---

### Formatting a Human-Readable Date

```python
from datetime import date

today = date(2026, 7, 14)

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

### Formatting a Datetime

`strftime()` also works with `datetime` objects.

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

---

### Creating a Date for a File Name

Formatted dates are often used in file names.

```python
from datetime import date

today = date.today()

file_name = (
    f"report-"
    f"{today.strftime('%Y%m%d')}.txt"
)

print(file_name)
```

Output:

```text
report-20260714.txt
```

---

### When Would I Use This?

Common situations include:

- Displaying dates to users
- Creating reports
- Generating file names
- Logging events
- Formatting dates for APIs
- Automation scripts

Example:

```python
from datetime import date

today = date.today()

print(
    f"Report generated on "
    f"{today.strftime('%d-%m-%Y')}"
)
```

---

### Related Problems

- Get Current Date
- Get Current Datetime
- Parse a Date String
- Write a Text File
- Append to a Text File

---

### Official Documentation

- date.strftime()
- datetime.strftime()

Python Documentation:

- https://docs.python.org/3/library/datetime.html#strftime-and-strptime-format-codes

---

### Summary

If you need to format a date, prefer:

```python
formatted = date_value.strftime(
    "%d-%m-%Y"
)
```

For machine-readable dates:

```python
formatted = date_value.strftime(
    "%Y-%m-%d"
)
```

For most Python applications, `strftime()` is the standard Pythonic solution for formatting dates and times.