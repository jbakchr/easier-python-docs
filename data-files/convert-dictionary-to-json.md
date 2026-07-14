---
layout: default
title: Convert a Dictionary to JSON
---

# Convert a Dictionary to JSON

---

## Problem

I have a Python dictionary.

For example:

```python
{
    "name": "Alice",
    "age": 30
}
```

I want to convert it into JSON.

This is often useful when:

- Sending data to an API
- Saving data to a file
- Printing structured data
- Exchanging data between applications

---

## Recommended Solution

Use `json.dumps()` from the `json` module.

```python
import json

data = {
    "name": "Alice",
    "age": 30
}

json_string = json.dumps(data)

print(json_string)
```

Output:

```json
{"name": "Alice", "age": 30}
```

---

## Why Use json?

The `json` module is part of the Python Standard Library.

It provides:

- A simple API for working with JSON
- Automatic conversion between Python objects and JSON
- Support for reading and writing JSON files
- No external dependencies

Converting a dictionary to JSON becomes straightforward:

```python
import json

json_string = json.dumps(data)
```

---

## What Does json.dumps() Return?

`json.dumps()` converts a Python object into a JSON string.

Example:

```python
import json

data = {
    "name": "Alice",
    "age": 30
}

json_string = json.dumps(data)

print(type(json_string))
```

Output:

```text
<class 'str'>
```

The result is a Python string containing JSON.

---

## Dictionary to JSON Conversion

Example dictionary:

```python
{
    "name": "Alice",
    "age": 30,
    "active": True
}
```

becomes:

```json
{
  "name": "Alice",
  "age": 30,
  "active": true
}
```

Notice that Python values are converted automatically.

---

## Common Python to JSON Conversions

| Python | JSON |
|----------|----------|
| dict | object |
| list | array |
| str | string |
| int / float | number |
| True | true |
| False | false |
| None | null |

Understanding these conversions makes JSON much easier to work with.

---

## Creating Pretty-Printed JSON

By default, JSON is compact.

```python
import json

print(json.dumps(data))
```

Output:

```json
{"name": "Alice", "age": 30}
```

For a more readable format:

```python
import json

print(
    json.dumps(
        data,
        indent=4
    )
)
```

Output:

```json
{
    "name": "Alice",
    "age": 30
}
```

This is often useful for debugging and documentation.

---

## Working with Lists and Nested Data

JSON can represent more than simple dictionaries.

```python
import json

data = {
    "name": "Alice",
    "languages": [
        "Python",
        "JavaScript"
    ],
    "address": {
        "city": "Copenhagen"
    }
}

print(
    json.dumps(
        data,
        indent=4
    )
)
```

Output:

```json
{
    "name": "Alice",
    "languages": [
        "Python",
        "JavaScript"
    ],
    "address": {
        "city": "Copenhagen"
    }
}
```

Nested dictionaries become nested JSON objects.

---

## Preserving Unicode Characters

By default, some non-English characters may be escaped.

```python
import json

data = {
    "name": "Jørgen"
}

print(json.dumps(data))
```

Output:

```json
{"name": "J\u00f8rgen"}
```

To preserve the original characters:

```python
import json

print(
    json.dumps(
        data,
        ensure_ascii=False
    )
)
```

Output:

```json
{"name": "Jørgen"}
```

This is often preferred when working with international text.

---

## Writing the JSON to a File

If you want to save the JSON to a file, use `json.dump()`.

```python
import json

with open(
    "user.json",
    "w",
    encoding="utf-8"
) as file:
    json.dump(
        data,
        file,
        indent=4
    )
```

This creates a JSON file on disk.

---

## When Would I Use This?

Common situations include:

- Sending API requests
- Saving configuration files
- Exporting application data
- Logging structured information
- Automation scripts
- Command-line applications

Example:

```python
import json

payload = {
    "message": "Hello"
}

json_payload = json.dumps(payload)
```

---

## Related Problems

- Read a JSON File
- Write a JSON File
- Pretty-Print JSON
- Convert JSON to a Dictionary
- Write a Text File

---

## Official Documentation

- `json.dumps()`
- `json.dump()`

Python Documentation:

- https://docs.python.org/3/library/json.html

---

## Summary

If you need to convert a dictionary into JSON, prefer:

```python
import json

json_string = json.dumps(data)
```

For readable output:

```python
import json

json_string = json.dumps(
    data,
    indent=4
)
```

To save the JSON to a file:

```python
import json

with open("data.json", "w") as file:
    json.dump(
        data,
        file,
        indent=4
    )
```

Remember:

```text
Python dictionary → JSON object
Python list       → JSON array
Python string     → JSON string
```

In modern Python code, `json.dumps()` is generally the recommended approach for converting Python dictionaries into JSON.