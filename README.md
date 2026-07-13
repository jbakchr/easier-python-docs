# easier-python-docs

> Find Python solutions by problem, not by module.

## Why?

The official Python documentation is excellent.

However, it is primarily designed as a **reference**. It works best when you already know:

- which module you need
- which class you need
- which function you need

Many Python developers (especially beginners and intermediates) often start somewhere else:

> I have a problem. What's the Pythonic way to solve it?

For example:

- How do I join a directory path and a filename?
- How do I read a text file?
- How do I check whether a file exists?
- How do I load a JSON file?
- How do I remove duplicates from a list?

The challenge is often not understanding the documentation.

The challenge is finding the right documentation in the first place.

## What is this?

**easier-python-docs** is a collection of small, problem-oriented pages that help connect common Python tasks with the relevant parts of the Python Standard Library.

Each page aims to answer:

1. What problem am I trying to solve?
2. What is the recommended Pythonic solution?
3. Are there alternative solutions?
4. Why might one solution be preferred?
5. Where can I learn more in the official Python documentation?

## Example

### Join Paths

**Problem**

I have a directory path and a filename.

I want:

```text
/path/to/project/README.md
```

**Recommended Solution**

```python
from pathlib import Path

path = Path.cwd() / "README.md"
```

**Alternative**

```python
os.path.join(...)
```

**Official Documentation**

- pathlib.Path
- pathlib.Path.cwd()
- pathlib.Path.__truediv__()

## Documentation Structure

The documentation is organized by problem domain rather than by Python module.

```text
Filesystem
Strings
Lists
Dictionaries
JSON
CSV
Dates & Times
Environment Variables
Subprocesses
Testing
CLI Applications
```

Within each category you will find "I want to..." style pages.

For example:

```text
Filesystem
├── Get current directory
├── Join paths
├── Read a file
├── Write a file
├── Check if a file exists
├── Create a directory
└── List files
```

## Design Principles

- Problem-oriented
- Beginner-friendly
- Small focused pages
- Modern Python practices
- Standard Library first
- Links back to the official documentation
- Learn the "why", not just the code

## Non-Goals

This project is not:

- A replacement for the official Python documentation
- A Python tutorial
- A complete Python reference
- A collection of copy-paste snippets without explanation

Instead, it aims to be a practical bridge between:

```text
"I have a problem"
```

and

```text
"I found the right Python documentation"
```

## Contributing

This project will grow gradually as new Python problems and solutions are discovered.

If you've ever searched for:

> "How do I do X in Python?"

and found the answer, that may be a great candidate for a new page.

## License

MIT
