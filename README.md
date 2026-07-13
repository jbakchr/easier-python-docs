# easier-python-docs

Find Python solutions by problem, not by module.

## Why?

The official Python documentation is excellent.

The challenge is usually not:

> How does this API work?

The challenge is often:

> Which API should I use?

Many developers start with a problem:

```text
How do I join paths?

How do I read a text file?

How do I check whether a file exists?

How do I load a JSON file?

How do I remove duplicates from a list?
```

The official documentation is primarily organized as a reference.

This project focuses on discovery.

Its goal is to help you find the right Python solution faster and then direct you to the relevant official documentation.

---

## What is this?

**easier-python-docs** is a collection of small, problem-oriented pages.

Each page focuses on a single task and answers questions such as:

- What problem am I trying to solve?
- What is the recommended Pythonic solution?
- Why is it recommended?
- What alternatives exist?
- Where can I learn more in the official documentation?

The goal is not to replace Python's documentation.

The goal is to help people discover the right documentation.

---

## Example

### Get File Extension

**Problem**

I have a file path:

```text
/home/user/projects/README.md
```

I want:

```text
.md
```

**Recommended Solution**

```python
from pathlib import Path

extension = Path("README.md").suffix
```

**Why Use This?**

`pathlib` provides a modern, readable, and cross-platform API for working with paths.

**Official Documentation**

- `pathlib.Path.suffix`

---

## Documentation Structure

Documentation is organized by problem domain rather than by module name.

Current and planned categories include:

```text
Filesystem
Strings
Lists
Dictionaries
JSON
Dates & Times
Environment Variables
Subprocesses
Command Line Applications
```

Within each category, pages are organized around practical tasks.

Example:

```text
Filesystem
├── Get current directory
├── Join paths
├── Check if a file exists
├── Read a text file
├── Write a text file
├── Get absolute path
├── Get file name from path
├── Get file extension
└── Get parent directory
```

---

## Design Principles

### Problem-Oriented

Pages start with a practical problem.

Not a module name.

Not a class name.

Not a function name.

### Small Focused Pages

Favor:

- one problem
- one solution
- one page

Over large tutorials and reference-style documentation.

### Modern Python

Prefer modern Python approaches when reasonable.

For example:

```python
from pathlib import Path
```

instead of older `os.path` approaches.

Alternative solutions are still documented when useful.

### Standard Library First

Prefer solutions from the Python Standard Library whenever possible.

### Learn the Why

Pages should explain:

- why a solution works
- when to use it
- why it may be preferred

Not just provide code snippets.

---

## Who Is This For?

This project is especially useful for:

- Python beginners
- Intermediate Python developers
- Developers moving to modern Python practices
- Anyone who has ever thought:

```text
I know Python probably has a solution.

I just don't remember what it's called.
```

---

## Website

The documentation is published using GitHub Pages.

Browse the documentation online:

```text
https://jbakchr.github.io/easier-python-docs/
```

---

## Non-Goals

This project is not:

- A replacement for docs.python.org
- A Python tutorial
- A complete Python reference
- A framework-specific guide
- A collection of random snippets

Instead, it aims to be a navigation layer between:

```text
I have a problem
```

and

```text
I found the right Python documentation
```

---

## Contributing

A page is usually worth creating if:

- It solves a practical Python problem
- It can be explained on a single page
- There is a clear recommended solution
- It naturally links to official Python documentation

A useful rule of thumb:

> If I would Google it, it is probably a good easier-python-docs page.

---

## License

MIT
