---
layout: default
title: Read a JSON File
---

# Read a JSON File

## Problem

I have a JSON file.

For example:

```json
{
  "name": "Alice",
  "age": 30
}
```

I want to load the data into my Python program.

## Recommended Solution

Use `json.load()` from the `json` module.

```python
import json

with open("user.json", "r", encoding="utf-8") as file:
    data = json.load(file)

print(data)
```

Output:

```python
{
    "name": "Alice",
    "age": 30
}
```

## Why Use json?

The `json` module is part of the Python Standard Library.

It provides:

- A simple API for working with JSON data
- Support for reading and writing JSON files
- Automatic conversion between JSON and Python objects
- No external dependencies

Reading a JSON file becomes straightforward:

```python
import json

with open("user.json", "r", encoding="utf-8") as file:
    data = json.load(file)
```

## What Does json.load() Return?

`json.load()` converts JSON into the corresponding Python data structure.

For example:

```json
{
  "name": "Alice",
  "age": 30
}
```

becomes:

```python
{
    "name": "Alice",
    "age": 30
}
```

Notice that the JSON object becomes a Python dictionary.

## JSON to Python Conversions

Common conversions include:

| JSON   | Python       |
| ------ | ------------ |
| object | dict         |
| array  | list         |
| string | str          |
| number | int or float |
| true   | True         |
| false  | False        |
| null   | None         |

Example:

```json
{
  "name": "Alice",
  "languages": ["Python", "JavaScript"],
  "active": true
}
```

becomes:

```python
{
    "name": "Alice",
    "languages": ["Python", "JavaScript"],
    "active": True
}
```

## Accessing Data

Once loaded, you can work with the data like any other Python object.

```python
import json

with open("user.json", "r", encoding="utf-8") as file:
    data = json.load(file)

print(data["name"])
```

Output:

```text
Alice
```

## Reading a JSON Array

JSON files sometimes contain arrays.

Example file:

```json
["Alice", "Bob", "Charlie"]
```

Reading the file:

```python
import json

with open("users.json", "r", encoding="utf-8") as file:
    users = json.load(file)

print(users)
```

Output:

```python
['Alice', 'Bob', 'Charlie']
```

The JSON array becomes a Python list.

## Using pathlib

If you prefer `pathlib`, combine it with `json.loads()`.

```python
import json
from pathlib import Path

content = Path("user.json").read_text(
    encoding="utf-8"
)

data = json.loads(content)

print(data)
```

This style fits nicely with modern Python code that already uses `pathlib`.

## What Happens if the File Does Not Exist?

Python raises a `FileNotFoundError`.

```python
import json

with open("missing.json", "r") as file:
    data = json.load(file)
```

Error:

```text
FileNotFoundError
```

You can avoid this by checking whether the file exists first.

```python
from pathlib import Path

file_path = Path("user.json")

if file_path.exists():
    data = json.loads(
        file_path.read_text(
            encoding="utf-8"
        )
    )
```

## What Happens if the JSON Is Invalid?

Python raises a `JSONDecodeError`.

Example:

```json
{
  "name": "Alice",
  "age":
}
```

Loading this file:

```python
import json

with open("user.json", "r") as file:
    data = json.load(file)
```

Error:

```text
json.JSONDecodeError
```

This usually means the file contains malformed JSON.

## When Would I Use This?

Common situations include:

- Loading configuration files
- Reading API responses saved to disk
- Working with application settings
- Processing exported data
- Command-line applications
- Automation scripts

Example:

```python
import json

with open("config.json", "r") as file:
    config = json.load(file)

print(config["database_url"])
```

## Related Problems

- Write a JSON File
- Pretty-Print JSON
- Convert JSON to a Dictionary
- Convert a Dictionary to JSON
- Read a Text File

## Official Documentation

- `json.load()`
- `json.loads()`
- `json.JSONDecodeError`

Python Documentation:

- https://docs.python.org/3/library/json.html

## Summary

If you need to read JSON from a file, prefer:

```python
import json

with open("user.json", "r", encoding="utf-8") as file:
    data = json.load(file)
```

If you are already using `pathlib`:

```python
import json
from pathlib import Path

data = json.loads(
    Path("user.json").read_text(
        encoding="utf-8"
    )
)
```

In modern Python code, `json.load()` is generally the recommended approach for reading JSON files.
