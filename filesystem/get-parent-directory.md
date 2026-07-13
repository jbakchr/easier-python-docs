---
layout: default
title: Get Parent Directory
---

# Get Parent Directory

## Problem

I have a file path.

For example:

```text
/home/user/projects/README.md
```

I want to get the directory that contains the file:

```text
/home/user/projects
```

## Recommended Solution

Use `Path.parent` from the `pathlib` module.

```python
from pathlib import Path

path = Path("/home/user/projects/README.md")

parent_directory = path.parent

print(parent_directory)
```

Output:

```text
/home/user/projects
```

## Why Use pathlib?

`pathlib` is the modern path-handling library in the Python Standard Library.

It provides:

- A clean and readable API
- Cross-platform support
- Object-oriented paths
- Convenient methods and attributes for working with files and directories

Getting the parent directory becomes simple and expressive:

```python
from pathlib import Path

parent_directory = Path("README.md").parent
```

## What Does Path.parent Return?

`Path.parent` returns the directory immediately above the current path.

Example:

```python
from pathlib import Path

path = Path("/home/user/projects/README.md")

print(path.parent)
```

Output:

```text
/home/user/projects
```

The filename is removed and only the containing directory remains.

## Getting the Parent of a Directory

`Path.parent` also works on directory paths.

```python
from pathlib import Path

path = Path("/home/user/projects")

print(path.parent)
```

Output:

```text
/home/user
```

The last directory component is removed.

## Going Up Multiple Levels

You can chain `.parent` to move further up the directory hierarchy.

```python
from pathlib import Path

path = Path("/home/user/projects/README.md")

print(path.parent.parent)
```

Output:

```text
/home/user
```

This can be useful when locating a project root directory.

## Alternative

Older code often uses `os.path.dirname()`.

```python
import os

parent_directory = os.path.dirname(
    "/home/user/projects/README.md"
)

print(parent_directory)
```

Output:

```text
/home/user/projects
```

This is still perfectly valid Python and remains common in existing codebases.

## Building Paths Relative to a Parent Directory

A common use case is locating related files.

```python
from pathlib import Path

path = Path("/home/user/projects/config/settings.json")

project_directory = path.parent

log_file = project_directory / "app.log"

print(log_file)
```

Output:

```text
/home/user/projects/config/app.log
```

## When Would I Use This?

Common situations include:

- Finding the directory containing a file
- Navigating project structures
- Locating configuration files
- Building paths relative to a known file
- Traversing directory hierarchies
- Command-line applications

Example:

```python
from pathlib import Path

script_directory = Path(__file__).parent

print(script_directory)
```

## Related Problems

- Get absolute path
- Get file name from path
- Get file extension
- Join paths
- Check if a directory exists

## Official Documentation

- `pathlib.Path.parent`
- `os.path.dirname()`

Python Documentation:

- https://docs.python.org/3/library/pathlib.html
- https://docs.python.org/3/library/os.path.html

## Summary

If you need the directory containing a file or directory, prefer:

```python
from pathlib import Path

parent_directory = Path(
    "/home/user/projects/README.md"
).parent
```

You can move higher up the directory hierarchy by chaining:

```python
path.parent.parent
```

Older code may use:

```python
import os

parent_directory = os.path.dirname(path)
```

In modern Python code, `pathlib.Path.parent` is generally the recommended approach.