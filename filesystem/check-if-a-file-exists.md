---
layout: default
title: Check if a File Exists
---

# Check if a File Exists

## Problem

I want to check whether a file exists before working with it.

For example, before reading a file, I want to know whether:

```text
README.md
```

actually exists in the current directory.

## Recommended Solution

Use `Path.exists()` from the `pathlib` module.

```python
from pathlib import Path

file_path = Path("README.md")

if file_path.exists():
    print("File exists")
else:
    print("File does not exist")
```

Example output:

```text
File exists
```

## Why Use `pathlib`?

`pathlib` is the modern path-handling library in the Python Standard Library.

It provides:

- A clean and readable API
- Cross-platform support
- Object-oriented paths
- Easy integration with other path operations

For example:

```python
from pathlib import Path

readme = Path.cwd() / "README.md"
```

## Checking Specifically for a File

`exists()` returns `True` for both files and directories.

If you want to make sure the path is a file, use `is_file()`.

```python
from pathlib import Path

file_path = Path("README.md")

if file_path.is_file():
    print("File exists")
else:
    print("File does not exist")
```

This is often the better choice when you specifically expect a file.

## Alternative

Older Python code often uses `os.path.exists()`.

```python
import os

if os.path.exists("README.md"):
    print("File exists")
```

This is still perfectly valid Python and is commonly found in existing codebases.

## When Would I Use This?

Common situations include:

- Reading configuration files
- Loading JSON files
- Checking whether a report has already been generated
- Avoiding "file not found" errors
- Creating a file only if it does not already exist

Example:

```python
from pathlib import Path

config_file = Path("config.json")

if config_file.exists():
    print("Loading configuration...")
```

## Related Problems

- Get current directory
- Join paths
- Read a file
- Write a file
- Check if a directory exists

## Official Documentation

- `pathlib.Path.exists()`
- `pathlib.Path.is_file()`
- `os.path.exists()`

Python Documentation:

- [pathlib](https://docs.pythonrary/pathlib.html
- [os.path](https://docs.python.org/3/library/os.path.html)


If you need to check whether a path exists:

```python
from pathlib import Path

Path("README.md").exists()
```

If you specifically need to verify that the path is a file:

```python
from pathlib import Path

Path("README.md").is_file()
```

In modern Python code, `pathlib` is generally the recommended approach.
