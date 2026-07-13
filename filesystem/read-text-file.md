---
layout: default
title: Read a Text File
---

# Read a Text File

## Problem

I want to read the contents of a text file.

For example, given a file:

```text
README.md
```

I want to load its contents into my Python program.


---


## Recommended Solution

Use `Path.read_text()` from the `pathlib` module.

```python
from pathlib import Path

content = Path("README.md").read_text()

print(content)
```

Example output:

```text
# My Project

This is my project.
```


---


## Why Use `pathlib`?

`pathlib` is the modern path-handling library in the Python Standard Library.

It provides:

- A clean and readable API
- Cross-platform support
- Object-oriented paths
- Convenient methods for reading and writing files

Reading a file becomes a single line of code:

```python
from pathlib import Path

content = Path("README.md").read_text()
```


---


## Reading a File Using UTF-8

If you want to be explicit about the file encoding, specify it using the `encoding` parameter.

```python
from pathlib import Path

content = Path("README.md").read_text(encoding="utf-8")
```

This is often a good practice when sharing code across different systems.


---


## Alternative

Many Python programs use the built-in `open()` function.

```python
with open("README.md", "r", encoding="utf-8") as file:
    content = file.read()

print(content)
```

This is still perfectly valid Python and is commonly found in existing codebases.


---


## Reading a File Line by Line

Sometimes you want to process individual lines.

```python
from pathlib import Path

lines = Path("README.md").read_text().splitlines()

for line in lines:
    print(line)
```

Alternatively:

```python
with open("README.md", "r", encoding="utf-8") as file:
    for line in file:
        print(line.strip())
```


---


## What Happens if the File Does Not Exist?

Python raises a `FileNotFoundError`.

```python
from pathlib import Path

content = Path("missing.txt").read_text()
```

Error:

```text
FileNotFoundError
```

You can avoid this by checking whether the file exists first.

```python
from pathlib import Path

file_path = Path("README.md")

if file_path.exists():
    content = file_path.read_text()
```


---


## When Would I Use This?

Common situations include:

- Reading configuration files
- Reading Markdown files
- Loading text-based data
- Reading log files
- Processing user-generated text
- Small command-line tools

Example:

```python
from pathlib import Path

notes = Path("notes.txt").read_text()
```


---


## Related Problems

- Get current directory
- Join paths
- Check if a file exists
- Write a text file
- List files in a directory


---


## Official Documentation

- `pathlib.Path.read_text()`
- `open()`

Python Documentation:

- https://docs.python.org/3/library/pathlib.html
- https://docs.python.org/3/library/functions.html#open


---


## Summary

If you need to read the contents of a text file, prefer:

```python
from pathlib import Path

content = Path("README.md").read_text()
```

To be explicit about encoding:

```python
from pathlib import Path

content = Path("README.md").read_text(encoding="utf-8")
```

In modern Python code, `pathlib` is generally the recommended approach for simple text file operations.
`
