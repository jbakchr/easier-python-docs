---
layout: default
title: Get File Extension
---

# Get File Extension

## Problem

I have a file path.

For example:

```text
/home/user/projects/README.md
```

I want to get:

```text
.md
```

so I can determine the type of file I am working with.

## Recommended Solution

Use `Path.suffix` from the `pathlib` module.

```python
from pathlib import Path

path = Path("/home/user/projects/README.md")

extension = path.suffix

print(extension)
```

Output:

```text
.md
```

## Why Use pathlib?

`pathlib` is the modern path-handling library in the Python Standard Library.

It provides:

- A clean and readable API
- Cross-platform support
- Object-oriented paths
- Convenient methods and attributes for working with files and directories

Getting a file extension becomes simple and expressive:

```python
from pathlib import Path

extension = Path("README.md").suffix
```

## What Does Path.suffix Return?

`Path.suffix` returns the file extension, including the leading dot.

Example:

```python
from pathlib import Path

path = Path("report.pdf")

print(path.suffix)
```

Output:

```text
.pdf
```

The dot is included because it is considered part of the extension.

## Files Without Extensions

Some files do not have an extension.

```python
from pathlib import Path

path = Path("README")

print(path.suffix)
```

Output:

```text

```

In this case, `Path.suffix` returns an empty string.

## Files with Multiple Extensions

Some filenames contain multiple extensions.

For example:

```text
archive.tar.gz
```

Using `Path.suffix`:

```python
from pathlib import Path

path = Path("archive.tar.gz")

print(path.suffix)
```

Output:

```text
.gz
```

Only the final extension is returned.

## Getting All Extensions

If you want all extensions, use `Path.suffixes`.

```python
from pathlib import Path

path = Path("archive.tar.gz")

print(path.suffixes)
```

Output:

```python
['.tar', '.gz']
```

This can be useful when working with compressed files.

## Alternative

Older code often uses `os.path.splitext()`.

```python
import os

filename, extension = os.path.splitext("README.md")

print(extension)
```

Output:

```text
.md
```

This is still perfectly valid Python and remains common in existing codebases.

## Removing the Extension

Sometimes you want the filename without the extension.

Use `Path.stem`.

```python
from pathlib import Path

path = Path("README.md")

print(path.stem)
```

Output:

```text
README
```

## When Would I Use This?

Common situations include:

- Determining file types
- Filtering files by extension
- Processing uploaded files
- Validating filenames
- Organizing files
- Building command-line tools

Example:

```python
from pathlib import Path

for file in Path("documents").iterdir():
    if file.suffix == ".pdf":
        print(file.name)
```

## Related Problems

- Get file name from path
- Get parent directory
- Get absolute path
- List files in a directory
- Find files recursively

## Official Documentation

- `pathlib.Path.suffix`
- `pathlib.Path.suffixes`
- `pathlib.Path.stem`
- `os.path.splitext()`

Python Documentation:

- https://docs.python.org/3/library/pathlib.html
- https://docs.python.org/3/library/os.path.html

## Summary

If you need the extension of a file, prefer:

```python
from pathlib import Path

extension = Path("README.md").suffix
```

If you need all extensions:

```python
from pathlib import Path

extensions = Path("archive.tar.gz").suffixes
```

If you need the filename without the extension:

```python
from pathlib import Path

filename = Path("README.md").stem
```

In modern Python code, `pathlib.Path.suffix` is generally the recommended approach.