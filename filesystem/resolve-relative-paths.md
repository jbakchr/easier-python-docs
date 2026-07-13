---
layout: default
title: Resolve Relative Paths
---

# Resolve Relative Paths

## Problem

I have a relative path.

For example:

```text
../config/settings.json
```

or:

```text
./data/users.csv
```

I want to determine the full path that Python will use.

## Recommended Solution

Use `Path.resolve()` from the `pathlib` module.

```python
from pathlib import Path

path = Path("../config/settings.json")

resolved_path = path.resolve()

print(resolved_path)
```

Example output:

```text
/home/user/project/config/settings.json
```

## Why Use pathlib?

`pathlib` is the modern path-handling library in the Python Standard Library.

It provides:

- A clean and readable API
- Cross-platform support
- Object-oriented paths
- Convenient methods for working with filesystem paths

Resolving a relative path becomes a single method call:

```python
from pathlib import Path

resolved_path = Path("../config/settings.json").resolve()
```

## What Is a Relative Path?

A relative path is interpreted relative to the current working directory.

For example:

```text
../config/settings.json
```

means:

```text
Go up one directory
↓
Enter the config directory
↓
Open settings.json
```

The actual location depends on where your program is running.

## Resolving a Relative File Path

Given:

```text
Current directory:
/home/user/project/src
```

and:

```text
../config/settings.json
```

then:

```python
from pathlib import Path

path = Path("../config/settings.json")

print(path.resolve())
```

might produce:

```text
/home/user/project/config/settings.json
```

## Resolving a Relative Directory Path

You can also resolve directories.

```python
from pathlib import Path

path = Path("../logs")

print(path.resolve())
```

Example output:

```text
/home/user/project/logs
```

## Resolving "." and ".."

Relative paths often contain:

```text
.
```

meaning:

```text
Current directory
```

and:

```text
..
```

meaning:

```text
Parent directory
```

Example:

```python
from pathlib import Path

path = Path("./data/../logs")

print(path.resolve())
```

Output:

```text
/home/user/project/logs
```

The resulting path is simplified automatically.

## Alternative

Older code often uses `os.path.abspath()`.

```python
import os

path = os.path.abspath("../config/settings.json")

print(path)
```

This is still perfectly valid Python and remains common in existing codebases.

## Using a Script's Location Instead of the Current Directory

A common pattern is to build paths relative to the location of the current Python file.

```python
from pathlib import Path

script_directory = Path(__file__).parent

config_file = (
    script_directory
    / "../config/settings.json"
).resolve()

print(config_file)
```

This can make applications more reliable because they do not depend on the current working directory.

## When Would I Use This?

Common situations include:

- Loading configuration files
- Working with project directories
- Building paths relative to scripts
- Logging file locations
- Debugging filesystem issues
- Command-line applications

Example:

```python
from pathlib import Path

data_file = Path("./data/users.csv").resolve()

print(data_file)
```

## Related Problems

- Get absolute path
- Get parent directory
- Join paths
- Get current directory
- Check if a file exists

## Official Documentation

- `pathlib.Path.resolve()`
- `pathlib.Path.parent`
- `os.path.abspath()`

Python Documentation:

- https://docs.python.org/3/library/pathlib.html
- https://docs.python.org/3/library/os.path.html

## Summary

If you need to determine the full location of a relative path, prefer:

```python
from pathlib import Path

resolved_path = Path(
    "../config/settings.json"
).resolve()
```

Relative paths depend on the current working directory.

Using:

```python
path.resolve()
```

converts them into a fully qualified path that is easier to understand, debug, and work with.

In modern Python code, `pathlib.Path.resolve()` is generally the recommended approach.