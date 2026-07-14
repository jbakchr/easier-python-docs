---
layout: default
title: Read Command-Line Arguments
---

## Read Command-Line Arguments

---

### Problem

I want to pass values to my Python script when I run it.

For example:

```bash
python greet.py Alice
```

I want my program to access:

```text
Alice
```

---

### Recommended Solution

Use `sys.argv`.

```python
import sys

name = sys.argv[1]

print(f"Hello, {name}!")
```

Run:

```bash
python greet.py Alice
```

Output:

```text
Hello, Alice!
```

---

### Why Use sys.argv?

`sys.argv` is part of Python's Standard Library.

It:

- Requires no external dependencies
- Provides access to command-line arguments
- Is simple and easy to understand
- Works in any Python script

For basic command-line applications, it is the recommended solution.

---

### What Is sys.argv?

`sys.argv` is a list containing the arguments passed to the program.

Example:

```python
import sys

print(sys.argv)
```

Run:

```bash
python greet.py Alice
```

Output:

```python
['greet.py', 'Alice']
```

The first item is always the script name.

---

### Understanding Argument Positions

Consider:

```bash
python app.py Alice 30
```

Then:

```python
import sys

print(sys.argv[0])
print(sys.argv[1])
print(sys.argv[2])
```

Output:

```text
app.py
Alice
30
```

Position:

```text
sys.argv[0] -> script name
sys.argv[1] -> first argument
sys.argv[2] -> second argument
```

---

### Reading Multiple Arguments

```python
import sys

name = sys.argv[1]
age = sys.argv[2]

print(name)
print(age)
```

Run:

```bash
python app.py Alice 30
```

Output:

```text
Alice
30
```

---

### What Happens if an Argument Is Missing?

Python raises an `IndexError`.

Example:

```python
import sys

name = sys.argv[1]
```

Run:

```bash
python app.py
```

Error:

```text
IndexError
```

---

### Checking Whether an Argument Was Provided

```python
import sys

if len(sys.argv) > 1:
    print(sys.argv[1])
else:
    print("No argument provided")
```

Run:

```bash
python app.py
```

Output:

```text
No argument provided
```

---

### Converting Argument Types

All command-line arguments are strings.

Example:

```python
import sys

age = sys.argv[1]

print(type(age))
```

Output:

```python
<class 'str'>
```

Convert values when necessary.

```python
import sys

age = int(sys.argv[1])

print(age + 1)
```

Run:

```bash
python app.py 30
```

Output:

```text
31
```

---

### Simple Example

```python
import sys

if len(sys.argv) < 2:
    print("Please provide a name")
else:
    print(
        f"Hello, {sys.argv[1]}!"
    )
```

Run:

```bash
python greet.py Alice
```

Output:

```text
Hello, Alice!
```

---

### When Would I Use This?

Common situations include:

- Command-line tools
- Automation scripts
- Utility programs
- Build scripts
- Data processing scripts
- Development tools

Example:

```python
import sys

file_name = sys.argv[1]

print(
    f"Processing {file_name}"
)
```

---

### Related Problems

- Accept Flags
- Display Help Text
- Read an Environment Variable
- Provide a Default Value
- Run a Command

---

### Official Documentation

- sys.argv

Python Documentation:

- https://docs.python.org/3/library/sys.html#sys.argv

---

### Summary

If you need to read command-line arguments, prefer:

```python
import sys

argument = sys.argv[1]
```

Arguments are stored in:

```python
sys.argv
```

which is a list of strings.

For simple command-line applications, `sys.argv` is the standard Pythonic solution for reading command-line arguments.