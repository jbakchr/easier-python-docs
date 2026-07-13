---
layout: default
title: Filesystem
---

# Filesystem

Working with files and directories is one of the most common tasks in Python.

This section focuses on practical filesystem-related problems and their recommended Pythonic solutions, primarily using the modern `pathlib` module from the Python Standard Library.

## I want to...

### Navigating Paths

- [Get the nt-directory
- [Join paths](join-paths)
lute pathGet a file name from a pathrectory

### Checking Files and Directories

- check-if-file-exists
- [Check if a directory exists](check-if-whether ang and Writing Files

- [Read a text file[Write a text file](write-text-file)
 Working with Directories

- create-directory
- [Create nesteddirectories
- [List files in a directory](list-files)
Operations

- copy-file
- [Move a file[Rename a file](rename-file)
 Recommended Modern Approach

Most pages in this section use `pathlib`.

Example:

```python
from pathlib import Path

readme = Path.cwd() / "README.md"
```

`pathlib` is generally preferred because it:

- Is included in the Python Standard Library
- Uses an object-oriented API
- Works across operating systems
- Produces readable code
- Is recommended in modern Python projects

Some pages may also show older alternatives using modules such as:

```python
os
os.path
shutil
```

These are still widely used and remain important to understand when reading existing code.

## Related Python Documentation

Official Python documentation:

- pathlib
- shutil
- os
- os.path

## Philosophy

Every page in this section aims to answer:

1. What problem am I trying to solve?
2. What is the recommended Pythonic solution?
3. Are there alternatives?
4. Why might one solution be preferred?
5. Where can I learn more in the official Python documentation?

The goal is not to replace the Python documentation.

The goal is to help you find the right Python documentation faster.
