---
layout: default
title: Accept Flags
---

## Accept Flags

---

### Problem

I want my Python program to accept command-line flags.

For example:

```bash
python app.py --debug
```

or:

```bash
python app.py --port 8080
```

I want Python to parse these values automatically.

---

### Recommended Solution

Use `argparse`.

```python
import argparse

parser = argparse.ArgumentParser()

parser.add_argument(
    "--debug",
    action="store_true"
)

args = parser.parse_args()

print(args.debug)
```

Run:

```bash
python app.py --debug
```

Output:

```text
True
```

---

### Why Use argparse?

`argparse` is part of Python's Standard Library.

It:

- Supports flags and options
- Automatically validates user input
- Generates help text
- Produces clearer command-line interfaces
- Requires no external dependencies

For most command-line applications, it is the recommended solution.

---

### What Is a Flag?

A flag is an optional command-line argument.

Example:

```bash
python app.py --debug
```

Flags typically enable or disable behavior.

Examples:

```text
--debug
--verbose
--force
--dry-run
```

---

### Creating a Boolean Flag

Use:

```python
action="store_true"
```

to create a flag that becomes `True` when provided.

```python
import argparse

parser = argparse.ArgumentParser()

parser.add_argument(
    "--debug",
    action="store_true"
)

args = parser.parse_args()

print(args.debug)
```

Run:

```bash
python app.py
```

Output:

```text
False
```

Run:

```bash
python app.py --debug
```

Output:

```text
True
```

---

### Accepting a Value

Some flags accept values.

Example:

```bash
python app.py --port 8080
```

Python:

```python
import argparse

parser = argparse.ArgumentParser()

parser.add_argument("--port")

args = parser.parse_args()

print(args.port)
```

Output:

```text
8080
```

---

### Converting Values

Arguments are returned as strings by default.

```python
import argparse

parser = argparse.ArgumentParser()

parser.add_argument("--port")

args = parser.parse_args()

print(type(args.port))
```

Output:

```python
<class 'str'>
```

Use `type=` to convert values automatically.

```python
import argparse

parser = argparse.ArgumentParser()

parser.add_argument(
    "--port",
    type=int
)

args = parser.parse_args()

print(args.port)
print(type(args.port))
```

Run:

```bash
python app.py --port 8080
```

Output:

```text
8080
<class 'int'>
```

---

### Providing a Default Value

You can provide a default value for a flag.

```python
import argparse

parser = argparse.ArgumentParser()

parser.add_argument(
    "--port",
    type=int,
    default=8080
)

args = parser.parse_args()

print(args.port)
```

Run:

```bash
python app.py
```

Output:

```text
8080
```

---

### Multiple Flags

Programs often use more than one flag.

```python
import argparse

parser = argparse.ArgumentParser()

parser.add_argument(
    "--debug",
    action="store_true"
)

parser.add_argument(
    "--port",
    type=int,
    default=8080
)

args = parser.parse_args()

print(args.debug)
print(args.port)
```

Run:

```bash
python app.py --debug --port 5000
```

Output:

```text
True
5000
```

---

### When Would I Use This?

Common situations include:

- Command-line tools
- Automation scripts
- Development utilities
- Build scripts
- Data processing programs
- System administration tools

Example:

```python
import argparse

parser = argparse.ArgumentParser()

parser.add_argument(
    "--verbose",
    action="store_true"
)

args = parser.parse_args()

if args.verbose:
    print("Verbose mode enabled")
```

---

### Related Problems

- [Read Command-Line Arguments](command-line-arguments/read-command-line-arguments)
- Display Help Text
- Read an Environment Variable
- Provide a Default Value
- Run a Command

---

### Official Documentation

- argparse.ArgumentParser
- add_argument()
- parse_args()

Python Documentation:

- https://docs.python.org/3/library/argparse.html

---

### Summary

If you need to accept command-line flags, prefer:

```python
import argparse

parser = argparse.ArgumentParser()

parser.add_argument(
    "--debug",
    action="store_true"
)

args = parser.parse_args()
```

For flags that accept values:

```python
parser.add_argument(
    "--port",
    type=int
)
```

For most Python command-line applications, `argparse` is the standard Pythonic solution for accepting flags and options.