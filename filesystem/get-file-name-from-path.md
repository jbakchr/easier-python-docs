---
layout: default
title: Get File Name from Path
---

# Get File Name from Path

## Problem

I have a file path.

For example:

```text
/home/user/projects/README.md
```

I want to get:

```text
README.md
```

without the rest of the path.

## Recommended Solution

Use `Path.name` from the `pathlib` module.

```python
from pathlib import Path

path = Path("/home/user/projects/README.md")

filename = path.name

print(filename)
```

Output:

```text
README.md
```

## Why Use pathlib?

`pathlib` is the modern path-handling library in the Python Standard Library.

It provides:

- A clean and readable API
- Cross-platform support
- Object-oriented paths
- Convenient methods and attributes for working with files and directories

Getting a file name becomes straightforward:

```python
from pathlib import Path

filename = Path("README.md").name
```

## What Does Path.name Return?

`Path.name` returns the final component of a path.

Example:

```python
from pathlib import Path

path = Path("/home/user/projects/README.md")

print(path.name)
```

Output:

```text
README.md
```

The directory information is not included.

## Directory Example

`Path.name` also works with directories.

```python
from pathlib import Path

path = Path("/home/user/projects")

print(path.name)
```

Output:

```text
projects
```

It always returns the last part of the path.

## Alternative

Older code often uses functions from the `os.path` module.

```python
import os

filename = os.path.basename("/home/user/projects/README.md")

print(filename)
```

Output:

```text
README.md
```

This is still perfectly valid Python and remains common in many existing codebases.

## Getting the File Name Without the Extension

Sometimes you want:

```text
README
```

instead of:

```text
README.md
```

Use `Path.stem`.

```python
from pathlib import Path

path = Path("/home/user/projects/README.md")

print(path.stem)
```

Output:

```text
README
```

## When Would I Use This?

Common situations include:

- Displaying file names to users
- Generating reports
- Working with uploaded files
- Renaming files
- Extracting metadata from paths
- Command-line applications

Example:

```python
from pathlib import Path

for path in Path("logs").glob("*.log"):
    print(path.name)
```

\*# Related Problems

- Get absolute\*path
- Get file extension
- Get pa\*ent directory
- Join paths
- List \*iles in a directory

## Official D\*cumentation

- `pathlib.Path.name`\*- `pathlib.Path.stem`
- `os.path.b*sename()`

Python Documentation:

- https://docs.python.org/3/library*pathlib.html

* https://docs.python*org/3/library/os.path.html

## Sum\*ary

If you need the file name fro\* a path, prefer:

```python
from p*thlib import Path

filename = Path*"/home/user/projects/README.md").n*me
```

If you need the file name \*ithout the extension:

```python
f*om pathlib import Path

filename =*Path("/home/user/projects/README.m*").stem
```

In modern Python code* `pathlib.Path.name` is generally *he recommended approach.
