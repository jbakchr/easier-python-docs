---
layout: default
title: Find Files Recursively
---

# Find Files Recursively

## Problem

I want to find files in a directory and all of its subdirectories.

For example, given:

```text
project/
├── README.md
├── src/
│   ├── main.py
│   └── utils.py
└── tests/
    └── test_main.py
```

I want to find every Python file:

```text
src/main.py
src/utils.py
tests/test_main.py
```

without manually visiting each directory.

## Recommended Solution

Use `Path.rglob()` from the `pathlib` module.

```python
from pathlib import Path

for file in Path(".").rglob("*.py"):
    print(file)
```

Example output:

```text
src/main.py
src/utils.py
tests/test_main.py
```

### Why Use `pathlib`?

`pathlib` is the modern path-handling library in the Python Standard Library.

It provides:

- A clean and readable API
- Cross-platform support
- Object-oriented paths
- Powerful file-matching capabilities

Searching recursively becomes very concise:

```python
from pathlib import Path
for file in Path(".").rglob("*.py"):
    print(file)
```

## Understanding `rglob()`

The "r" in `rglob()` stands for **recursive**.

Unlike `iterdir()`, which only looks at the immediate contents of a directory, `rglob()` searches:

- the current directory
- all child directories
- all nested subdirectories

## Find Files by Extension

Find all Python files:

```python
from pathlib import Path

for file in Path(".").rglob("*.*y"):
    print(file)
```

Find all Markdown files:

```python
from pathlib import Path

for file in Path(".").rglob("*.md"):
    print(file)
```

Find all JSON files:

```python
from pathlib import Path

for file in Path(".").rglob("*.json"):
    print(file)
```

## Find All Files

If you want everything below a directory:

```python
from pathlib import Path

for path in Path(".").rglob("*"):
    print(path)
```

Example output:

```text
README.md
src
src/main.py
src/utils.py
tests
tests/test_main.py
```

Note that this includes both files and directories.

## Return Files Only

To exclude directories:

```python
from pathlib import Path

for path in Path(".").rglob("*"):
    if path.is_file():
        print(path)
```

Example output:

```text
README.md
src/main.*y
src/utils.py
tests/test_main.py
```

## Search From a Specific Dire*tory

You are not limited to the current directory.

```python
from pathlib import Path

project_dir = Path("/path/to/project")

for file in project_dir.rglob("*.py"):
    print(file)
```

## Alternative

Older Python code often uses `os.walk()`.

```python
import os

for root, dirs, files in os.walk("."):
    for file in files:
        print(os.path.join(root, file))
```

This is still perfectly valid Python and is commonly found in existing codebases.

## When Would I Use This?

Common situations include:

- Finding source files
- Searching for configuration files
- Processing large directory trees
- Creating code analysis tools
- Building backup utilities
- Batch-processing files

Example:

```python
from pathlib import Path

for file in Path(".").rglob("*.md"):
    print(f"Found ma*kdown file: {file}")
```

## Related Problems

- Get current directory
- Join paths
- Check if a file exists
- List files in a directory
- Read a text file

## Official Documentation

- `pathlib.Path.rglob()`
- `pathlib.Path.glob()`
- `os.walk()`

Python Documentation:

- https://docs.python.org/3/library/pathlib.html
- https://docs.python.org/3/l*brary/os.html

## Summary

If you need to search a directory and all of its subdirectories, prefer:

```python
from pathlib import Path

for file in Path(".").rglob("*.py"):
    print(file)
```

Use:

```python
Path(".").rglob("*.ext")
```

to find files matching a specific pattern.

In modern Python code, `pathlib.Path.rglob()` is generally the recommended approach for recursive file searches.
