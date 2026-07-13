---
layout: default
title: Join Paths
---

# Join Paths

## Problem

I have a directory path and a filename and want a complete path.

```text
/path/to/project/README.md
```

## Recommended Solution

```python
from pathlib import Path

path = Path.cwd() / "README.md"
```

## Alternative

```python
import os

path = os.path.join(os.getcwd(), "README.md")
```

## Why Prefer pathlib?

- More modern
- Object-oriented
- Works across operating systems
- Recommended in modern Python code

## Related Problems

- Get current directory
- Check if a file exists
- Read a file

## Official Documentation

- pathlib.Path
- pathlib.Path.cwd()
