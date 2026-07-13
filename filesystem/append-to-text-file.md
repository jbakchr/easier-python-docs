---
layout: default
title: Append to a Text File
---

# Append to a Text File

## Problem

I want to add text to the end of an existing file without replacing its current contents.

For example, given a file:

```text
log.txt
```

containing:

```text
Application started
```

I want to add:

```text
Application finished
```

so that the file becomes:

```text
Application started
Application finished
```

## Recommended Solution

Use the built-in `open()` function with append mode (`"a"`).

```python
with open("log.txt", "a", encoding="utf-8") as file:
    file.write("Application finished\n")
```

The text is added to the end of the file.

If the file does not exist, it will be created automatically.

## Why Use `open()`?

Unlike reading and writing files, `pathlib` does not provide an `append_text()` method.

Appending is therefore typically done using `open()` and append mode.

```python
with open("notes.txt", "a", encoding="utf-8") as file:
    file.write("New note\n")
```

This is the standard Python approach.

## Understanding File Modes

Common file modes include:

| Mode | Meaning |
|--------|--------|
| `"r"` | Read a file |
| `"w"` | Write a file (overwrite existing contents) |
| `"a"` | Append to a file |
| `"x"` | Create a file and fail if it already exists |

For appending text, use:

```python
"a"
```

## Appending Multiple Lines

You can append several lines at once.

```python
with open("log.txt", "a", encoding="utf-8") as file:
    file.write("Step 1 completed\n")
    file.write("Step 2 completed\n")
    file.write("Step 3 completed\n")
```

Result:

```text
Application started
Step 1 completed
Step 2 completed
Step 3 completed
```

## Using `pathlib` with `open()`

If you are already using `pathlib`, you can combine it with `open()`.

```python
from pathlib import Path

log_file = Path("log.txt")

with log_file.open("a", encoding="utf-8") as file:
    file.write("Application finished\n")
```

This fits nicely with other `pathlib`-based filesystem code.

## When Would I Use This?

Common situations include:

- Writing log files
- Recording application activity
- Storing user actions
- Keeping audit trails
- Building simple command-line tools
- Saving notes incrementally

Example:

```python
from datetime import datetime

with open("log.txt", "a", encoding="utf-8") as file:
    file.write(f"{datetime.now()}: Job completed\n")
```

## Related Problems

- Get current directory
- Join paths
- Check if a file exists
- Read a text file
- Write a text file

## Official Documentation

- `open()`

Python Documentation:

- [Built-in Functions — open()](https://docs.python.org/3/# Summary

If you need to add text to the end of a file without overwriting it, use append mode:

```python
with open("log.txt", "a", encoding="utf-8") as file:
    file.write("New line\n")
```

Remember:

- `"w"` overwrites a file
- `"a"` appends to a file

Use append mode whenever you want to preserve the file's existing contents.
