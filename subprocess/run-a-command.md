---
layout: default
title: Run a Command
---

## Run a Command

---

### Problem

I want to run an external command from my Python program.

For example:

```bash
git status
```

or:

```bash
ls
```

I want Python to execute the command and wait for it to finish.

---

### Recommended Solution

Use `subprocess.run()`.

```python
import subprocess

subprocess.run(["git", "status"])
```

Output:

```text
On branch main
nothing to commit, working tree clean
```

The exact output will depend on the command.

---

### Why Use subprocess.run()?

`subprocess.run()` is part of Python's Standard Library.

It:

- Requires no external dependencies
- Runs external commands safely
- Supports command arguments
- Waits for the command to finish
- Works on all major operating systems

For most situations, it is the recommended way to run commands from Python.

---

### How Does subprocess.run() Work?

Command arguments are passed as a list.

```python
import subprocess

subprocess.run([
    "git",
    "status"
])
```

This is equivalent to running:

```bash
git status
```

from a terminal.

---

### Running a Simple Command

```python
import subprocess

subprocess.run(["pwd"])
```

Output:

```text
/Users/alice/projects
```

The exact output will depend on your system.

---

### Passing Arguments

Commands often require arguments.

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

### Checking Whether the Command Succeeded

Use:

```python
check=True
```

to raise an exception if the command fails.

```python
import subprocess

subprocess.run(
    ["git", "status"],
    check=True
)
```

If the command exits with a non-zero status, Python raises:

```text
subprocess.CalledProcessError
```

---

### Running a Python Script

You can use Python to launch another Python program.

```python
import subprocess

subprocess.run([
    "python",
    "hello.py"
])
```

This is equivalent to:

```bash
python hello.py
```

---

### Running a Command in a Specific Directory

Use `cwd`.

```python
import subprocess

subprocess.run(
    ["git", "status"],
    cwd="/path/to/project"
)
```

Python runs the command inside the specified directory.

---

### What Happens if the Command Does Not Exist?

Python raises a `FileNotFoundError`.

```python
import subprocess

subprocess.run([
    "does-not-exist"
])
```

Error:

```text
FileNotFoundError
```

This usually means the command is not available on your system.

---

### When Would I Use This?

Common situations include:

- Running Git commands
- Automation scripts
- Build scripts
- Calling system utilities
- Running external programs
- Development tools

Example:

```python
import subprocess

subprocess.run([
    "git",
    "pull"
])
```

---

### Related Problems

- Capture Command Output
- Check Command Exit Status
- Pass Arguments to a Command
- Read Command-Line Arguments
- Accept Flags

---

### Official Documentation

- subprocess.run()
- subprocess.CalledProcessError

Python Documentation:

- https://docs.python.org/3/library/subprocess.html

---

### Summary

If you need to run an external command, prefer:

```python
import subprocess

subprocess.run([
    "git",
    "status"
])
```

To detect failures:

```python
subprocess.run(
    ["git", "status"],
    check=True
)
```

For most Python applications, `subprocess.run()` is the standard Pythonic solution for running external commands.