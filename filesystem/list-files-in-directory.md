---
layout: default
title: List Files in a Directory
---

# List Files in a Directory

## Problem

I want to see which files and directories exist inside a directory.

For example, given:

```text
my-project/
├── README.md
├── main.py
├── requirements.txt
└── data/
```

I want my Python program to discover and work with those files.

## Recommended Solution

Use `Path.iterdir()` from the `pathlib` module.

```python
from pathlib import Path

for item in Path(".").iterdir():
    print(item)
```

Example output:

```text
README.md
main.py
requirements.txt
data
```

## Why Use `pathlib`?

`pathlib` is the modern path-handling library in the Python Standard Library.

It provides:

- A clean and readable API
- Cross-platform support
- Object-oriented paths
- Easy integration with other filesystem operations

For example:

```python
from pathlib import Path

for item in Path.cwd().iterdir():
    print(item)
```

## Listing Only Files

If you only want files, use `is_file()`.

```python
from pathlib import Path

for item in Path(".").iterdir():
    if item.is_file():
        print(item)
```

Example output:

```text
README.md
main.py
requirements.txt
```

## Listing Only Directories

If you only want directories, use `is_dir()`.

```python
from pathlib import Path

for item in Path(".").iterdir():
    if item.is_dir():
        print(item)
```

Example output:

```text
data
```

## Getting File Names Only

By default, `Path` objects are printed.

If you only want the file or directory name:

```python
from pathlib import Path

for item in Path(".").iterdir():
    print(item.name)
```

Example output:

```text
README.md
main.py
requirements.txt
data
```

## Listing Files in Another Directory

You are not limited to the current directory.

```python
from pathlib import Path

directory = Path("/path/to/project")

for item in directory.iterdir():
    print(item.name)
```

## Alternative

Older Python code often uses `os.listdir()`.

```python
import os

for item in os.listdir("."):
    print(item)
```

This is still perfectly valid Python and is commonly found in existing codebases.

## What About Recursive Searches?

`iterdir()` only lists items in a single directory.

It does **not** search subdirectories.

For example:

```text
project/
├── README.md
└── src/
    └── main.py
```

Using `iterdir()` on `project` will return:

```text
README.md
src
```

but not:

```text
src/main.py
```

Searching recursively is covered in:

- Find files recursively

## When Would I Use This?

Common situations include:

- Finding files to process
- Building command-line tools
- Generating reports
- Working with configuration files
- Batch processing data
- Exploring directory contents

Example:

```python
from pathlib import Path

for file in Path(".").iterdir():
    if file.is_file():
        print(f"Processing {file.name}")
```

## Related Problems

- Get current directory
- Join paths
- Check if a file exists
- Read a text file
- Find files recursively

## Official Documentation

- `pathlib.Path.iterdir()`
- `pathlib.Path.is_file()`
- `pathlib.Path.is_dir()`
- `os.listdir()`

Python Documentation:

- https://docs.python.org/3/library/pathlib.html
- https://docs.python.org/3/library/os.html

## Summary

If you need to list the contents of a directory, prefer:

```python
from pathlib import Path

for item in Path(".").iterdir():
    print(item.name)
```

Use:

```python
item.is_file()
```

to work only with files, and:

```python
item.is_dir()
```

to work only with directories.

In modern Python code, `pathlib` is generally the recommended approach for listing directory contents.
