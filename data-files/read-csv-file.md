---
layout: default
title: Read a CSV File
---

## Read a CSV File

---

### Problem

I have a CSV file.

For example:

```csv
name,age
Alice,30
Bob,25
Charlie,35
```

I want to read the data into my Python program.

---

### Recommended Solution

Use the `csv` module from the Python Standard Library.

```python
import csv

with open(
    "users.csv",
    newline="",
    encoding="utf-8"
) as file:
    reader = csv.reader(file)

    for row in reader:
        print(row)
```

Output:

```python
['name', 'age']
['Alice', '30']
['Bob', '25']
['Charlie', '35']
```

---

### Why Use csv?

The `csv` module is part of the Python Standard Library.

It provides:

- Built-in CSV support
- No external dependencies
- Support for different CSV formats
- Simple APIs for reading and writing CSV files

For most CSV files, it is the recommended solution.

---

### What Does csv.reader() Return?

`csv.reader()` returns an iterator that produces rows from the file.

Each row is returned as a list of strings.

Example:

```python
import csv

with open(
    "users.csv",
    newline="",
    encoding="utf-8"
) as file:
    reader = csv.reader(file)

    for row in reader:
        print(type(row))
```

Output:

```python
<class 'list'>
<class 'list'>
<class 'list'>
<class 'list'>
```

---

### Reading Rows Into a List

Sometimes you want all rows at once.

```python
import csv

with open(
    "users.csv",
    newline="",
    encoding="utf-8"
) as file:
    rows = list(csv.reader(file))

print(rows)
```

Output:

```python
[
    ['name', 'age'],
    ['Alice', '30'],
    ['Bob', '25'],
    ['Charlie', '35']
]
```

---

### Reading CSV Data as Dictionaries

CSV files often contain headers.

You can use `csv.DictReader()` to access values by column name.

```python
import csv

with open(
    "users.csv",
    newline="",
    encoding="utf-8"
) as file:
    reader = csv.DictReader(file)

    for row in reader:
        print(row)
```

Output:

```python
{
    'name': 'Alice',
    'age': '30'
}

{
    'name': 'Bob',
    'age': '25'
}

{
    'name': 'Charlie',
    'age': '35'
}
```

---

### Using pathlib

If you are already using `pathlib`, you can combine it with `csv.reader()`.

```python
import csv
from pathlib import Path

with Path("users.csv").open(
    newline="",
    encoding="utf-8"
) as file:
    reader = csv.reader(file)

    for row in reader:
        print(row)
```

---

### What Happens if the File Does Not Exist?

Python raises a `FileNotFoundError`.

```python
import csv

with open("missing.csv") as file:
    rows = list(csv.reader(file))
```

Error:

```text
FileNotFoundError
```

You can check whether the file exists first.

```python
from pathlib import Path

file_path = Path("users.csv")

if file_path.exists():
    print("File exists")
```

---

### When Would I Use This?

Common situations include:

- Importing spreadsheet data
- Processing exported reports
- Reading application data
- Data analysis scripts
- Automation tasks
- Command-line tools

Example:

```python
import csv

with open(
    "sales.csv",
    newline="",
    encoding="utf-8"
) as file:
    reader = csv.DictReader(file)

    for row in reader:
        print(row["name"])
```

---

### Related Problems

- Write a CSV File
- Read a JSON File
- Write a JSON File
- Read a Text File
- Check if a File Exists

---

### Official Documentation

- csv.reader()
- csv.DictReader()

Python Documentation:

- https://docs.python.org/3/library/csv.html

---

### Summary

If you need to read a CSV file, prefer:

```python
import csv

with open(
    "users.csv",
    newline="",
    encoding="utf-8"
) as file:
    reader = csv.reader(file)

    for row in reader:
        print(row)
```

If your CSV file contains headers, consider:

```python
csv.DictReader(file)
```

The `csv` module is the standard Pythonic solution for reading CSV files.