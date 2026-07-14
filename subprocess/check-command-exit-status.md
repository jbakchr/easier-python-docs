---
layout: default
title: Check Command Exit Status
---

## Check Command Exit Status

---

### Problem

I want to know whether a command succeeded or failed.

For example:

```bash
git status
```

I want Python to check the command's result and react accordingly.

---

### Recommended Solution

Use `result.returncode`.

```python
import subprocess

result = subprocess.run(
    ["git", "status"]
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

### Why Use returncode?

`returncode` is provided by `subprocess.run()`.

It:

- Requires no external dependencies
- Indicates whether a command succeeded
- Works with any external command
- Allows programs to respond to failures

For most situations, it is the recommended way to check command success.

---

### What Is an Exit Status?

When a command finishes running, it returns an exit status.

Typically:

```text
0 = Success
Non-zero = Failure
```

Examples:

```text
0
1
2
127
```

The exact meaning depends on the command.

---

### Accessing the Exit Status

Use:

```python
result.returncode
```

Example:

```python
import subprocess

result = subprocess.run(
    ["git", "status"]
)

print(result.returncode)
```

Output:

```text
0
```

---

### Checking for Success

A common pattern is:

```python
import subprocess

result = subprocess.run(
    ["git", "status"]
)

if result.returncode == 0:
    print("Success")
else:
    print("Failure")
```

Output:

```text
Success
```

---

### Checking for Failure

You can also explicitly detect failures.

```python
import subprocess

result = subprocess.run(
    ["git", "status"]
)

if result.returncode != 0:
    print("Command failed")
```

---

### Using check=True

Another option is:

```python
check=True
```

Example:

```python
import subprocess

subprocess.run(
    ["git", "status"],
    check=True
)
```

If the command fails, Python raises:

```text
subprocess.CalledProcessError
```

This can simplify error handling when failure should stop the program.

---

### Example: Handling Success and Failure

```python
import subprocess

result = subprocess.run(
    ["git", "status"]
)

if result.returncode == 0:
    print(
        "Git command succeeded"
    )
else:
    print(
        "Git command failed"
    )
```

---

### Capturing Output and Checking Status

You can combine exit status checking with output capture.

```python
import subprocess

result = subprocess.run(
    ["git", "status"],
    capture_output=True,
    text=True
)

if result.returncode == 0:
    print(result.stdout)
else:
    print(result.stderr)
```

---

### When Would I Use This?

Common situations include:

- Automation scripts
- Build scripts
- CI/CD pipelines
- System administration tools
- Running Git commands
- Calling external programs

Example:

```python
import subprocess

result = subprocess.run(
    ["git", "pull"]
)

if result.returncode == 0:
    print("Repository updated")
```

---

### Related Problems

- Run a Command
- Capture Command Output
- Pass Arguments to a Command
- Read Command-Line Arguments
- Accept Flags

---

### Official Documentation

- subprocess.run()
- subprocess.CompletedProcess
- subprocess.CalledProcessError

Python Documentation:

- https://docs.python.org/3/library/subprocess.html

---

### Summary

If you need to check whether a command succeeded, prefer:

```python
import subprocess

result = subprocess.run(
    ["git", "status"]
)

print(result.returncode)
```

Use:

```python
result.returncode == 0
```

to check for success.

For most Python applications, `returncode` is the standard Pythonic solution for checking command exit status.