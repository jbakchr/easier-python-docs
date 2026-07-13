---
layout: default
title: Write a Text File
---

# Write a Text File

## Problem

I want to write text to a file.

For example, I want to create a file:

```text
README.md
```

and store some text inside it.

## Recommended Solution

Use `Path.write_text()` from the `pathlib` module.

```python
from pathlib import Path

Path("README.md").write_text("# My Project")
```

The file will be created if it does not already exist.

If the file already exists, its contents will be replaced.

## Why Use `pathlib`?

`pathlib` is the modern path-handling library in the Python Standard Library.

It provides:

- A clean and readable API
- Cross-platform support
- Object-oriented paths
- Convenient methods for reading and writing files

Writing a text file becomes a single line of code:

```python
from pathlib import Path

Path("notes.txt").write_text("Hello, World!")
```

## Writing Using UTF-8

It is often a good idea to be explicit about the file encoding.

```python
from pathlib import Path

Path("README.md").write_text(
    "# My Project",
    encoding="utf-8"
)
```

This helps ensure your code behaves consistently across different systems.

## Alternative

Many Python programs use the built-in `open()` function.

```python
with open("README.md", "w", encoding="utf-8") as file:
    file.write("# My Project")
```

This is still perfectly valid Python and is commonly found in existing codebases.

## What Happens If the File Already Exists?

`write_text()` replaces the existing contents.

Example:

Suppose `notes.txt` contains:

```text
Old content
```

Running:

```python
from pathlib import Path

Path("notes.txt").write_text("New content")
```

results in:

```text
New content
```

The previous contents are overwritten.

## Writing Multiple Lines

You can include newline characters (`\n`) in your text.

```python
from pathlib import Path

Path("notes.txt").write_text(
    "First line\nSecond line\nThird line"
)
```

Result:

```text
First line
Second line
Third line
```

## When Would I Use This?

Common situations include:

- Creating configuration files
- Writing reports
- Generating Markdown files
- Saving logs
- Exporting text data
- Creating temporary files

Example:

```python
from pathlib import Path

report = """
Daily Report

Status: OK
"""

Path("report.txt").write_text(report)
```

## Related Problems

- Get current directory
- Join paths
- Check if a file exists
- Read a text file
- Append to a text file

## Official Documentation

- `pathlib.Path.write_text()`
- `open()`

Python Documentation:

- https://docs.python.org/3/library/pathlib.html
- https://docs.python.org/3/library/functions.html#open

## Summary

If you need to write text to a file, prefer:

```python
from pathlib import Path

Path("README.md").write_text(
    "# My Project",
    encoding="utf-8"
)
```

Remember that `write_text()` will create the file if it does not exist and overwrite it if it does.
