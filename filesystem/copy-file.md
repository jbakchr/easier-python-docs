---
layout: default
title: Copy a File
---

# Copy a File

---

## Problem

I want to copy a file in Python.

For example, I want to copy:

```text
report.txt
```

to:

```text
backup/report.txt
```

while keeping the original file unchanged.

---

## Recommended Solution

Use `shutil.copy()` from the Python Standard Library.

```python
from shutil import copy

copy("report.txt", "backup/report.txt")
```

After running the code:

```text
report.txt
backup/report.txt
```

Both files exist.

The original file remains unchanged.

---

## Why Use shutil?

The `shutil` module is the standard way to perform high-level file operations in Python.

It provides:

- Simple file-copying functions
- Cross-platform support
- Readable code
- Common filesystem utilities

Copying a file becomes a single line of code:

```python
from shutil import copy

copy("report.txt", "backup/report.txt")
```

---

## Copy Using pathlib

If you are already using `pathlib`, you can combine it with `shutil.copy()`.

```python
from pathlib import Path
from shutil import copy

source = Path("report.txt")
destination = Path("backup") / "report.txt"

copy(source, destination)
```

This provides the benefits of `pathlib` while still using Python's standard file-copying functionality.

---

## What Happens If the Destination File Exists?

By default, the destination file is overwritten.

```python
from shutil import copy

copy("report.txt", "backup/report.txt")
```

If:

```text
backup/report.txt
```

already exists, the contents are replaced with the copied file.

Be careful when copying files to existing locations.

---

## Copy File Metadata

If you also want to preserve metadata such as modification times, use:

```python
from shutil import copy2

copy2("report.txt", "backup/report.txt")
```

`copy2()` copies:

- File contents
- Modification times
- Access times
- Other available metadata

This is often useful when creating backups.

---

## Copy to a Different File Name

You can copy a file and give the copy a new name.

```python
from shutil import copy

copy("report.txt", "report-backup.txt")
```

After running:

```text
report.txt
report-backup.txt
```

Both files exist.

---

## Alternative

You could manually read and write the file:

```python
with open("report.txt", "rb") as source:
    data = source.read()

with open("backup/report.txt", "wb") as destination:
    destination.write(data)
```

However, `shutil.copy()` is simpler, clearer, and less error-prone.

---

## When Would I Use This?

Common situations include:

- Creating backups
- Copying configuration files
- Moving data between directories
- Preparing test data
- Generating reports
- Archiving project files

Example:

```python
from shutil import copy

copy("config.json", "backup/config.json")
```

---

## Related Problems

- Move a File
- Rename a File
- Delete a File
- [Check if a File Exists](check-if-a-file-exists)
- [Create a Directory](create-directory)
- List Files in a Directory

---

## Official Documentation

- shutil.copy()
- shutil.copy2()

Python Documentation:

- https://docs.python.org/3/library/shutil.html

---

## Summary

If you need to copy a file, prefer:

```python
from shutil import copy

copy("report.txt", "backup/report.txt")
```

If you also want to preserve file metadata:

```python
from shutil import copy2

copy2("report.txt", "backup/report.txt")
```

In modern Python code, `shutil.copy()` is generally the recommended approach for copying files.