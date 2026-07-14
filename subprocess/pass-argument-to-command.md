---
layout: default
title: Pass Arguments to a Command
---

## Pass Arguments to a Command

---

### Problem

I want to run an external command from Python.

For example:

```bash
git log --oneline
```

or:

```bash
ls -l
```

I want to pass arguments to the command safely and correctly.

---

### Recommended Solution

Pass the command and its arguments as a list to `subprocess.run()`.

```python
import subprocess

subprocess.run([
    "git",
    "log",
    "--oneline"
])
```

This is equivalent to:

```bash
git log --oneline
```

---

### Why Use a List?

`subprocess.run()` expects the command and its arguments as separate list items.

It:

- Is simple and readable
- Avoids manual string parsing
- Handles spaces correctly
- Is the recommended Python approach

For most situations, each argument should be a separate item in the list.

---

### Running a Simple Command

```python
import subprocess

subprocess.run([
    "ls",
    "-l"
])
```

This is equivalent to:

```bash
ls -l
```

---

### Understanding the Argument List

Consider:

```python
import subprocess

subprocess.run([
    "git",
    "commit",
    "-m",
    "Initial commit"
])
```

This is equivalent to:

```bash
git commit -m "Initial commit"
```

Each argument is a separate element.

```python
[
    "git",
    "commit",
    "-m",
    "Initial commit"
]
```

---

### Passing a File Name

A common use case is processing files.

```python
import subprocess

file_name = "report.txt"

subprocess.run([
    "cat",
    file_name
])
```

This is equivalent to:

```bash
cat report.txt
```

---

### Building Arguments Dynamically

Arguments can be created at runtime.

```python
import subprocess

branch = "main"

subprocess.run([
    "git",
    "checkout",
    branch
])
```

Equivalent to:

```bash
git checkout main
```

---

### Running a Python Script with Arguments

```python
import subprocess

subprocess.run([
    "python",
    "hello.py",
    "Alice"
])
```

This is equivalent to:

```bash
python hello.py Alice
```

---

### Combining Arguments with Output Capture

Arguments work naturally with output capture.

```python
import subprocess

result = subprocess.run(
    [
        "git",
        "branch"
    ],
    capture_output=True,
    text=True
)

print(result.stdout)
```

---

### Combining Arguments with Exit Status Checks

```python
import subprocess

result = subprocess.run(
    [
        "git",
        "status"
    ]
)

if result.returncode == 0:
    print("Success")
```

---

### Why Not Build a Command String?

Avoid manually building command strings when possible.

Instead of:

```python
command = (
    "git checkout main"
)
```

Prefer:

```python
[
    "git",
    "checkout",
    "main"
]
```

Passing arguments separately is usually clearer and easier to work with.

---

### When Would I Use This?

Common situations include:

- Running Git commands
- Automation scripts
- Build scripts
- System administration tools
- Processing files
- Running external programs

Example:

```python
import subprocess

file_name = "data.csv"

subprocess.run([
    "wc",
    "-l",
    file_name
])
```

---

### Related Problems

- Run a Command
- Capture Command Output
- Check Command Exit Status
- Read Command-Line Arguments
- Accept Flags

---

### Official Documentation

- subprocess.run()

Python Documentation:

- https://docs.python.org/3/library/subprocess.html

---

### Summary

If you need to pass arguments to a command, prefer:

```python
import subprocess

subprocess.run([
    "git",
    "log",
    "--oneline"
])
```

Each argument should be a separate item in the list:

```python
[
    "command",
    "argument1",
    "argument2"
]
```

For most Python applications, passing arguments as a list is the standard Pythonic solution when using `subprocess.run()`.