---
layout: default
title: Create a Directory
---

# Create a Directory

## Problem

I want to create a directory from Python.

For example, I want to create:

```text
data/
```

inside my current working directory.

## Recommended Solution

Use `Path.mkdir()` from the `pathlib` module.

```python
from pathlib import Path

Path("data").mkdir()
```

After running the code:

```text
project/
└── data/
```

The directory is created if it does not already exist.

## Why Use `pathlib`?

`pathlib` is the modern path-handling library in the Python Standard Library.

It provides:

- A clean and readable API
- Cross-platform support
- Object-oriented paths
- Easy integration with other filesystem operations

Creating a directory becomes a single line of code:

```python
from pathlib import Path

Path("data").mkdir()
```

## What Happens If the Directory Already Exists?

By default, Python raises a `FileExistsError`.

```python
from pathlib import Path

Path("data").mkdir()
```

Error:

```text
FileExistsError
```

## Create the Directory Only If It Does Not Already Exist

To avoid the error, use:

```python
from pathlib import Path

Path("data").mkdir(exist_ok=True)
```

This creates the directory if it does not exist and does nothing if it already exists.

This is often the most convenient option.

## Create a Directory in Another Location

You are not limited to the current directory.

```python
from pathlib import Path

Path("/tmp/data").mkdir()
```

Or:

```python
from pathlib import Path

project_dir = Path.cwd()

(project_dir / "data").mkdir()
```

## Creating Nested Directories

Suppose you want to create:

```text
data/reports/2026/
```

If some of the parent directories do not exist, use:

```python
from pathlib import Path

Path("data/reports/2026").mkdir(parents=True)
```

This creates all missing parent directories automatically.

To avoid errors if the directories already exist:

```python
from pathlib import Path

Path("data/reports/2026").mkdir(
    parents=True,
    exist_ok=True
)
```

## Alternative

Older Python code often uses `os.mkdir()`.

```python
import os

os.mkdir("data")
```

Or:

```python
import os

os.makedirs("data/reports/2026")
```

These approaches are still valid and are commonly found in existing codebases.

## When Would I Use This?

Common situations include:

- Creating data directories
- Creating output folders for reports
- Creating log directories
- Building command-line tools
- Setting up project structures
- Storing generated files

Example:

```python
from pathlib import Path

output_dir = Path("output")

output_dir.mkdir(exist_ok=True)
```

## Related Problems

- Get current directory
- Join paths
- Check if a directory exists
- Write a text file
- List files in a directory

## Official Documentation

- `pathlib.Path.mkdir()`
- `os.mkdir()`
- `os.makedirs()`

Python Documentation:

- https://docs.python.org/3/library/pathlib.html
- https://docs.python.org/3/library/os.html

## Summary

If you need to create a directory, prefer:

```python
from pathlib import Path

Path("data").mkdir()
```

If the directory may already exist:

```python
from pathlib import Path

Path("data").mkdir(exist_ok=True)
```

If you need to create multiple levels of directories:

```python
from pathlib import Path

Path("data/reports/2026").mkdir(
    parents=True,
    exist_ok=True
)
```

In modern Python code, `pathlib.Path.mkdir()` is generally the recommended approach for creating directories.
