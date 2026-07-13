---
layout: default
title: Get Current Directory
---

# Get Current Directory

## Problem

I want to find the current working directory.

For example, if my Python script is running from:

```text
/home/jonas/my-project
```

I want to get that path in my Python code.

## Recommended Solution

Use `Path.cwd()` from the `pathlib` module.

```python
from pathlib import Path

cwd = Path.cwd()

print(cwd)
```

Example output:

```text
/home/jonas/my-project
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

## Alternative

Older Python code often uses `os.getcwd()`.

```python
import os

cwd = os.getcwd()

print(cwd)
```

Example output:

```text
/home/jonas/my-project
```

This is still perfectly valid Python and is commonly found in existing codebases.

## When Would I Use This?

Common situations include:

- Building file paths
- Reading or writing files in the current directory
- CLI applications
- Debugging path-related problems
- Loading configuration files

Example:

```python
from pathlib import Path

config_file = Path.cwd() / "config.json"
```

## Related Problems

- Join paths
- Check if a file exists
- Read a file
- Write a file
- List files in a directory

## Official Documentation

- `pathlib.Path.cwd()`
- `os.getcwd()`

Python Documentation:

- https://docs.python.org/3/library/pathlib.html
- https://docs.python.org/3/library/os.html

## Summary

If you need the current working directory, prefer:

```python
from pathlib import Path

cwd = Path.cwd()
```

It is the modern and recommended approach for working with filesystem paths in Python.
`
