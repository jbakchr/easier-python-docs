---
layout: default
title: Capture Command Output
---

## Capture Command Output

---

### Problem

I want to run a command from Python.

For example:

```bash
git status
```

Instead of printing the output to the terminal, I want to store the result in a Python variable.

---

### Recommended Solution

Use `subprocess.run()` with `capture_output=True`.

```python
import subprocess

result = subprocess.run(
    ["git", "status"],
    capture_output=True,
    text=True
)

print(result.stdout)
```

Output:

```text
On branch main
nothing to commit, working tree clean
```

The exact output will depend on the command.

---

### Why Use capture_output=True?

`capture_output=True` tells Python to collect the command's output instead of displaying it directly in the terminal.

It:

- Requires no external dependencies
- Captures standard output
- Captures error output
- Works with any command
- Integrates naturally with `subprocess.run()`

For most situations, it is the recommended way to capture command output.

---

### What Does subprocess.run() Return?

`subprocess.run()` returns a `CompletedProcess` object.

```python
import subprocess

result = subprocess.run(
    ["git", "status"],
    capture_output=True,
    text=True
)

print(type(result))
```

Output:

```python
<class 'subprocess.CompletedProcess'>
```

The object contains useful information about the command.

---

### Accessing Standard Output

Use:

```python
result.stdout
```

Example:

```python
import subprocess

result = subprocess.run(
    ["pwd"],
    capture_output=True,
    text=True
)

print(result.stdout)
```

Output:

```text
/home/user/projects
```

The exact output will depend on your system.

---

### Accessing Error Output

Use:

```python
result.stderr
```

Example:

```python
import subprocess

result = subprocess.run(
    ["git", "not-a-command"],
    capture_output=True,
    text=True
)

print(result.stderr)
```

Output:

```text
error: unknown command
```

The exact output will depend on the command.

---

### Why Use text=True?

Without:

```python
text=True
```

Python returns bytes.

Example:

```python
import subprocess

result = subprocess.run(
    ["pwd"],
    capture_output=True
)

print(result.stdout)
```

Output:

```python
b'/home/user/projects\n'
```

Using:

```python
text=True
```

returns a normal Python string.

```python
import subprocess

result = subprocess.run(
    ["pwd"],
    capture_output=True,
    text=True
)

print(result.stdout)
```

Output:

```text
/home/user/projects
```

---

### Checking Whether the Command Succeeded

Use:

```python
result.returncode
```

Example:

```python
import subprocess

result = subprocess.run(
    ["git", "status"],
    capture_output=True,
    text=True
)

print(result.returncode)
```

Output:

```text
0
```

A return code of:

```text
0
```

usually indicates success.

---

### Capturing a Git Command

```python
import subprocess

result = subprocess.run(
    ["git", "branch"],
    capture_output=True,
    text=True
)

print(result.stdout)
```

Output:

```text
* main
```

The exact output will depend on your repository.

---

### When Would I Use This?

Common situations include:

- Automation scripts
- Running Git commands
- Processing command output
- System administration tools
- Build scripts
- Development utilities

Example:

```python
import subprocess

result = subprocess.run(
    ["pwd"],
    capture_output=True,
    text=True
)

current_directory = result.stdout.strip()

print(current_directory)
```

---

### Related Problems

- Run a Command
- Check Command Exit Status
- Pass Arguments to a Command
- Read Command-Line Arguments
- Accept Flags

---

### Official Documentation

- subprocess.run()
- subprocess.CompletedProcess

Python Documentation:

- https://docs.python.org/3/library/subprocess.html

---

### Summary

If you need to capture the output of a command, prefer:

```python
import subprocess

result = subprocess.run(
    ["git", "status"],
    capture_output=True,
    text=True
)

print(result.stdout)
```

Use:

```python
result.stdout
```

to access standard output and:

```python
result.stderr
```

to access error output.

For most Python applications, `capture_output=True` with `subprocess.run()` is the standard Pythonic solution for capturing command output.