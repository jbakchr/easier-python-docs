---
layout: default
title: Display Help Text
---

## Display Help Text

---

### Problem

I am building a command-line application.

I want users to be able to run:

```bash
python app.py --help
```

and see instructions for using the program.

---

### Recommended Solution

Use `argparse`.

```python
import argparse

parser = argparse.ArgumentParser(
    description="Example application"
)

parser.parse_args()
```

Run:

```bash
python app.py --help
```

Output:

```text
usage: app.py [-h]

Example application

options:
  -h, --help  show this help message and exit
```

---

### Why Use argparse?

`argparse` is part of Python's Standard Library.

It:

- Automatically generates help text
- Documents available arguments
- Produces consistent command-line interfaces
- Requires no external dependencies

For most command-line applications, it is the recommended solution.

---

### Help Text Is Generated Automatically

Simply creating an `ArgumentParser` enables:

```bash
--help
```

Example:

```python
import argparse

parser = argparse.ArgumentParser()

parser.parse_args()
```

Run:

```bash
python app.py --help
```

Output:

```text
usage: app.py [-h]

options:
  -h, --help  show this help message and exit
```

---

### Adding a Description

A description helps explain what your program does.

```python
import argparse

parser = argparse.ArgumentParser(
    description="Generate a report"
)

parser.parse_args()
```

Run:

```bash
python app.py --help
```

Output:

```text
usage: app.py [-h]

Generate a report

options:
  -h, --help  show this help message and exit
```

---

### Documenting Flags

Help text becomes more useful when arguments include descriptions.

```python
import argparse

parser = argparse.ArgumentParser(
    description="Generate a report"
)

parser.add_argument(
    "--output",
    help="Output file name"
)

args = parser.parse_args()
```

Run:

```bash
python app.py --help
```

Output:

```text
usage: app.py [-h] [--output OUTPUT]

Generate a report

options:
  -h, --help       show this help message and exit
  --output OUTPUT  Output file name
```

---

### Documenting Boolean Flags

```python
import argparse

parser = argparse.ArgumentParser()

parser.add_argument(
    "--verbose",
    action="store_true",
    help="Enable verbose output"
)

args = parser.parse_args()
```

Run:

```bash
python app.py --help
```

Output:

```text
usage: app.py [-h] [--verbose]

options:
  -h, --help  show this help message and exit
  --verbose   Enable verbose output
```

---

### Creating a Simple Command-Line Tool

```python
import argparse

parser = argparse.ArgumentParser(
    description="Backup files"
)

parser.add_argument(
    "--source",
    help="Source directory"
)

parser.add_argument(
    "--destination",
    help="Destination directory"
)

args = parser.parse_args()
```

Help output:

```bash
python backup.py --help
```

```text
usage: backup.py [-h]
                 [--source SOURCE]
                 [--destination DESTINATION]

Backup files

options:
  -h, --help
  --source SOURCE
  --destination DESTINATION
```

---

### Why Is Help Text Useful?

Help text makes command-line programs easier to use.

Users can discover:

- Available arguments
- Available flags
- Required values
- What the program does

without reading the source code.

---

### When Would I Use This?

Common situations include:

- Command-line tools
- Automation scripts
- Developer utilities
- System administration tools
- Data processing programs
- Internal tooling

Example:

```bash
python app.py --help
```

This is often the first command users run when learning a tool.

---

### Related Problems

- Read Command-Line Arguments
- Accept Flags
- Provide a Default Value
- Read an Environment Variable
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

If you want your command-line application to display help text, prefer:

```python
import argparse

parser = argparse.ArgumentParser(
    description="My application"
)

parser.parse_args()
```

Users can then run:

```bash
python app.py --help
```

to see automatically generated usage information.

For most Python command-line applications, `argparse` is the standard Pythonic solution for displaying help text.