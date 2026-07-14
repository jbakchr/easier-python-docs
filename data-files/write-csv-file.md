---
layout: default
title: Write a CSV File
---

## Write a CSV File

---

### Problem

I have data in my Python program.

For example:

```python
[
    ["Alice", 30],
    ["Bob", 25],
    ["Charlie", 35]
]
```

I want to save the data to a CSV file.

---

### Recommended Solution

Use the `csv` module from the Python Standard Library.

```python
import csv

rows = [
    ["Alice", 30],
    ["Bob", 25],
    ["Charlie", 35]
]

with open(
    "users.csv",
    "w",
    newline="",
    encoding="utf-8"
) as file:
    writer = csv.writer(file)

    writer.writerows(rows)
```

Contents of `users.csv`:

```csv
Alice,30
Bob,25
Charlie,35
```

---

### Why Use csv?

The `csv` module is part of the Python Standard Library.

It provides:

- Built-in CSV support
- No external dependencies
- Correct handling of commas and quotes
- Simple APIs for writing tabular data

For most CSV files, it is the recommended solution.

---

### Writing a Single Row

Use `writer.writerow()` to write one row at a time.

```python
import csv

with open(
    "users.csv",
    "w",
    newline="",
    encoding="utf-8"
) as file:
    writer = csv.writer(file)

    writer.writerow(["Alice", 30])
```

Contents:

```csv
Alice,30
```

---

### Writing Multiple Rows

Use `writer.writerows()` to write multiple rows.

```python
import csv

rows = [
    ["Alice", 30],
    ["Bob", 25],
    ["Charlie", 35]
]

with open(
    "users.csv",
    "w",
    newline="",
    encoding="utf-8"
) as file:
    writer = csv.writer(file)

    writer.writerows(rows)
```

Contents:

```csv
Alice,30
Bob,25
Charlie,35
```

---

### Writing Column Headers

CSV files often include a header row.

```python
import csv

rows = [
    ["Alice", 30],
    ["Bob", 25],
    ["Charlie", 35]
]

with open(
    "users.csv",
    "w",
    newline="",
    encoding="utf-8"
) as file:
    writer = csv.writer(file)

    writer.writerow(["name", "age"])
    writer.writerows(rows)
```

Contents:

```csv
name,age
Alice,30
Bob,25
Charlie,35
```

---

### Writing Dictionaries

If your data is stored as dictionaries, use `csv.DictWriter()`.

```python
import csv

users = [
    {"name": "Alice", "age": 30},
    {"name": "Bob", "age": 25},
    {"name": "Charlie", "age": 35}
]

with open(
    "users.csv",
    "w",
    newline="",
    encoding="utf-8"
) as file:
    writer = csv.DictWriter(
        file,
        fieldnames=["name", "age"]
    )

    writer.writeheader()
    writer.writerows(users)
```

Contents:

```csv
name,age
Alice,30
Bob,25
Charlie,35
```

---

### Using pathlib

If you are already using `pathlib`, you can combine it with `csv.writer()`.

```python
import csv
from pathlib import Path

with Path("users.csv").open(
    "w",
    newline="",
    encoding="utf-8"
) as file:
    writer = csv.writer(file)

    writer.writerow(["Alice", 30])
```

---

### Why Use newline=""?

When writing CSV files, Python recommends using:

```python
newline=""
```

This helps ensure rows are written correctly across different operating systems.

---

### When Would I Use This?

Common situations include:

- Exporting application data
- Creating reports
- Saving spreadsheet-compatible files
- Data analysis scripts
- Automation tasks
- Command-line tools

Example:

```python
import csv

sales = [
    ["January", 1500],
    ["February", 1800],
    ["March", 2100]
]

with open(
    "sales.csv",
    "w",
    newline="",
    encoding="utf-8"
) as file:
    writer = csv.writer(file)

    writer.writerow(
        ["month", "revenue"]
    )

    writer.writerows(sales)
```

---

### Related Problems

- Read a CSV File
- Read a JSON File
- Write a JSON File
- Write a Text File
- Append to a Text File

---

### Official Documentation

- csv.writer()
- csv.DictWriter()

Python Documentation:

- https://docs.python.org/3/library/csv.html

---

### Summary

If you need to write a CSV file, prefer:

```python
import csv

with open(
    "users.csv",
    "w",
    newline="",
    encoding="utf-8"
) as file:
    writer = csv.writer(file)

    writer.writerows(rows)
```

If your data is stored as dictionaries, consider:

```python
csv.DictWriter()
```

The `csv` module is the standard Pythonic solution for writing CSV files.