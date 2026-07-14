---
layout: default
title: Write a JSON File
---

# Write a JSON File

---

## Problem

I have Python data.

For example:

```python
{
    "name": "Alice",
    "age": 30
}
```

I want to save it as a JSON file.

---

## Recommended Solution

Use `json.dump()` from the `json` module.

```python
import json

data = {
    "name": "Alice",
    "age": 30
}

with open("user.json", "w", encoding="utf-8") as file:
    json.dump(data, file)
```

This creates a file containing:

```json
{ "name": "Alice", "age": 30 }
```

---

## Why Use json?

The `json` module is part of the Python Standard Library.

It provides:

- A simple API for working with JSON data
- Support for reading and writing JSON files
- Automatic conversion between Python objects and JSON
- No external dependencies

Writing a JSON file becomes straightforward:

```python
import json

with open("user.json", "w", encoding="utf-8") as file:
    json.dump(data, file)
```

---

## What Does json.dump() Do?

`json.dump()` converts Python objects into JSON and writes the result directly to a file.

Example:

```python
data = {
    "name": "Alice",
    "age": 30
}
```

becomes:

```json
{
  "name": "Alice",
  "age": 30
}
```

inside the file.

---

## Python to JSON Conversions

Common conversions include:

| Python      | JSON   |
| ----------- | ------ |
| dict        | object |
| list        | array  |
| str         | string |
| int / float | number |
| True        | true   |
| False       | false  |
| None        | null   |

Example:

```python
data = {
    "name": "Alice",
    "languages": ["Python", "JavaScript"],
    "active": True
}
```

becomes:

```json
{
  "name": "Alice",
  "languages": ["Python", "JavaScript"],
  "active": true
}
```

---

## Writing Pretty-Printed JSON

By default, JSON is written on a single line.

```python
import json

with open("user.json", "w", encoding="utf-8") as file:
    json.dump(data, file)
```

Output:

```json
{ "name": "Alice", "age": 30 }
```

For more readable JSON, use `indent`.

```python
import json

with open("user.json", "w", encoding="utf-8") as file:
    json.dump(
        data,
        file,
        indent=4
    )
```

Output:

```json
{
  "name": "Alice",
  "age": 30
}
```

This is often preferred for configuration files and files intended to be edited by humans.

---

## Using pathlib

If you prefer `pathlib`, combine it with `json.dumps()`.

```python
import json
from pathlib import Path

data = {
    "name": "Alice",
    "age": 30
}

content = json.dumps(
    data,
    indent=4
)

Path("user.json").write_text(
    content,
    encoding="utf-8"
)
```

This style works well in projects that already use `pathlib`.

---

## Writing Unicode Characters

JSON often contains text from different languages.

To preserve the original characters, use:

```python
import json

data = {
    "name": "Jørgen"
}

with open("user.json", "w", encoding="utf-8") as file:
    json.dump(
        data,
        file,
        ensure_ascii=False
    )
```

Without `ensure_ascii=False`, some characters may be escaped.

---

## Overwriting Existing Files

Opening a file with:

```python
open("user.json", "w")
```

will overwrite the existing file.

Example:

```python
import json

with open("user.json", "w", encoding="utf-8") as file:
    json.dump(data, file)
```

If the file already exists, its previous contents are replaced.

---

## When Would I Use This?

Common situations include:

- Saving configuration files
- Exporting application data
- Storing program settings
- Saving API responses
- Automation scripts
- Command-line applications

Example:

```python
import json

settings = {
    "theme": "dark",
    "font_size": 14
}

with open("settings.json", "w") as file:
    json.dump(
        settings,
        file,
        indent=4
    )
```

---

## Related Problems

- Read a JSON File
- Pretty-Print JSON
- Convert a Dictionary to JSON
- Convert JSON to a Dictionary
- Write a Text File

---

## Official Documentation

- `json.dump()`
- `json.dumps()`

Python Documentation:

- https://docs.python.org/3/library/json.html

---

## Summary

If you need to write JSON to a file, prefer:

```python
import json

with open("user.json", "w", encoding="utf-8") as file:
    json.dump(data, file)
```

For human-readable JSON:

```python
import json

with open("user.json", "w", encoding="utf-8") as file:
    json.dump(
        data,
        file,
        indent=4
    )
```

If you are already using `pathlib`:

```python
import json
from pathlib import Path

Path("user.json").write_text(
    json.dumps(data, indent=4),
    encoding="utf-8"
)
```

In modern Python code, `json.dump()` is generally the recommended approach for writing JSON files.
