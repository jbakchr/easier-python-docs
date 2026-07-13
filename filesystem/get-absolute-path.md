---
layout: default
title: Get Absolute Path
---

# Get Absolute Path

## Problem

I have a relative path.

I want the full absolute path on my system.

For example:

```text
README.md
```

becomes:

```text
/home/jonas/projects/easier-python-docs/README.md
```

## Recommended Solution

Use `Path.resolve()` from the `pathlib` module.

```python
from pathlib import Path

path = Path("README.md").resolve()

print(path)
```

Example output:

```text
/home/jonas/projects/easier-python-docs/README.md
```

## Why Use pathlib?

`pathlib` is the modern path-handling library in the Python Standard Library.

It provides:

- A clean and readable API
- Cross-platform support
- Object-oriented paths
- Convenient methods for common filesystem tasks

Converting a relative path to an absolute path becomes a single method call:

```python
from pathlib import Path

absolute_path = Path("README.md").resolve()
```

## What Is an Absolute Path?

An absolute path contains the full location of a file or directory.

Relative path:

```text
README.md
```

Absolute path:

```text
/home/jonas/projects/easier-python-docs/README.md
```

Relative paths depend on the current working directory.

Absolute paths do not.

## Getting the Absolute Path of a Directory

You can also resolve directory paths.

```python
from pathlib import Path

directory = Path("docs").resolve()

print(directory)
```

Example output:

```text
/home/jonas/projects/easier-python-docs/docs
```

## Alternative

Older code often uses `os.path.abspath()`.

```python
import os

path = os.path.abspath("README.md")

print(path)
```

This is still perfectly valid Python and remains common in existing codebases.

## Resolving the Current Directory

To get the absolute path of the current working directory:

```python
from pathlib import Path

current_directory = Path.cwd()

print(current_directory)
```

Example output:

```text
/home/jonas/projects/easier-python-docs
```

## When Would I Use This?

Common situations include:

- Displaying full file locations
- Logging file paths
- Passing paths to external tools
- Comparing file locations
- Building paths relative to the current project
- Debugging filesystem issues

Example:

```python
from pathlib import Path

config_file = Path("config.json").resolve()

print(config_file)
```

## Related Problems

- Get current directory
- Join paths
- Get file name from path
- Get file extension
- Get parent directory
- Check if a file exists

## Official Documentation

- `pathlib.Path.resolve()`
- `pathlib.Path.cwd()`
- `os.path.abspath()`

Python Documentation:

- https://docs.python.org/3/library/pathlib.html
- https://docs.python.org/3/library/os.path.html

## Summary

If you need the full absolute path of a file or directory, prefer:

```python
from pathlib import Path

absolute_path = Path("README.md").resolve()
```

Older code may use:

```python
import os

absolute_path = os.path.abspath("README.md")
```

In modern Python code, `pathlib.Path.resolve()` is generally the recommended approach.
