---
layout: default
title: Check if a Directory Exists
---

# Check if a Directory Exists

## Problem

I want to check whether a directory exists before using it.

For example, before writing files to:

```text
output/
```

I want to verify that the directory is already present.

## Recommended Solution

Use `Path.is_dir()` from the `pathlib` module.

```python
from pathlib import Path

directory = Path("output")

if directory.is_dir():
    print("Directory exists")
else:
    print("Directory does not exist")
```

Example output:

```text
Directory exists
```

## Why Use `is_dir()`?

`is_dir()` specifically checks whether a path exists and is a directory.

This is often what you really want to know.

```python
from pathlib import Path

Path("output").is_dir()
```

returns:

```python
True
```

only if:

- the path exists
- and it is a directory

## Why Not Use `exists()`?

You might see code like:

```python
from pathlib import Path

Path("output").exists()
```

This works, but it returns `True` for both:

```text
Directories
Files
```

For example:

```python
Path("README.md").exists()
```

and:

```python
Path("output").exists()
```

may both return:

```python
True
```

If you specifically need a directory, `is_dir()` is usually the better choice.

## Example: Create a Directory Only If It Does Not Exist

```python
from pathlib import Path

output_dir = Path("output")

if not output_dir.is_dir():
    output_dir.mkdir()
```

This creates the directory only when it is missing.

## Create the Directory Regardless

Often an even simpler approach is:

```python
from pathlib import Path

Path("output").mkdir(exist_ok=True)
```

This avoids the need for a check altogether.

See:

- Create a directory

## Alternative

Older Python code often uses `os.path.isdir()`.

```python
import os

if os.path.isdir("output"):
    print("Directory exists")
```

This is still perfectly valid Python and is commonly found in existing codebases.

## What About Parent Directories?

You can check any directory path.

```python
from pathlib import Path

project_dir = Path("/home/jonas/project")

if project_dir.is_dir():
    print("Project directory exists")
```

## When Would I Use This?

Common situations include:

- Checking for output directories
- Verifying configuration folders
- Building command-line tools
- Preparing data directories
- Validating user input
- Performing filesystem checks

Example:

```python
from pathlib import Path

reports_dir = Path("reports")

if reports_dir.is_dir():
    print("Generating report...")
```

## Related Problems

- Get current directory
- Join paths
- Check if a file exists
- Create a directory
- List files in a directory

## Official Documentation

- `pathlib.Path.is_dir()`
- `pathlib.Path.exists()`
- `os.path.isdir()`

Python Documentation:

- https://docs.python.org/3/library/pathlib.html
- https://docs.python.org/3/library/os.path.html

## Summary

If you need to check whether a directory exists, prefer:

```python
from pathlib import Path

Path("output").is_dir()
```

Use:

```python
Path("output").exists()
```

when you only care whether a path exists.

Use:

```python
Path("output").is_dir()
```

when you specifically need to know whether the path is a directory.

In modern Python code, `pathlib.Path.is_dir()` is generally the recommended approach.
