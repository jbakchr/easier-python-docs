---
layout: default
title: Convert JSON to a Dictionary
---

# Convert JSON to a Dictionary

---

## Problem

I have JSON data.

For example:

```json
{
  "name": "Alice",
  "age": 30
}
```

I want to convert it into a Python dictionary so I can work with the data in my program.

---

## Recommended Solution

Use `json.loads()` from the `json` module.

```python
import json

json_string = '''
{
    "name": "Alice",
    "age": 30
}
'''

data = json.loads(json_string)

print(data)
```

Output:

```python
{
    "name": "Alice",
    "age": 30
}
```

---

## Why Use json?

The `json` module is part of the Python Standard Library.

It provides:

- A simple API for working with JSON data
- Automatic conversion between JSON and Python objects
- Support for reading and writing JSON
- No external dependencies

Converting JSON to a dictionary becomes straightforward:

```python
import json

data = json.loads(json_string)
```

---

## What Does json.loads() Do?

`json.loads()` converts a JSON string into the corresponding Python object.

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

The JSON object becomes a Python dictionary.

---

## Accessing Values

Once converted, you can use dictionary operations.

```python
import json

json_string = '''
{
    "name": "Alice",
    "age": 30
}
'''

data = json.loads(json_string)

print(data["name"])
```

Output:

```text
Alice
```

---

## JSON Objects Become Dictionaries

Example JSON:

```json
{
  "name": "Alice",
  "age": 30,
  "active": true
}
```

Converted to Python:

```python
{
    "name": "Alice",
    "age": 30,
    "active": True
}
```

Notice that:

```json
true
```

becomes:

```python
True
```

---

## JSON Arrays Become Lists

JSON does not always produce dictionaries.

Example:

```json
[
  "Python",
  "JavaScript",
  "Go"
]
```

```python
import json

data = json.loads(
    '["Python", "JavaScript", "Go"]'
)

print(data)
```

Output:

```python
['Python', 'JavaScript', 'Go']
```

The JSON array becomes a Python list.

---

## Common JSON to Python Conversions

| JSON | Python |
|--------|--------|
| object | dict |
| array | list |
| string | str |
| number | int or float |
| true | True |
| false | False |
| null | None |

Understanding these conversions helps make JSON easier to work with.

---

## Reading JSON from a File

If your JSON is stored in a file, use `json.load()`.

```python
import json

with open("user.json", "r", encoding="utf-8") as file:
    data = json.load(file)

print(data)
```

If the JSON file contains an object, the result is typically a dictionary.

---

## What Happens if the JSON Is Invalid?

Python raises a `JSONDecodeError`.

Example:

```python
import json

json.loads(
    '{"name":}'
)
```

Error:

```text
json.JSONDecodeError
```

This usually indicates malformed JSON.

---

## When Would I Use This?

Common situations include:

- Processing API responses
- Working with configuration data
- Reading JSON from files
- Receiving JSON from web services
- Automation scripts
- Command-line applications

Example:

```python
import json

response = '''
{
    "status": "ok",
    "count": 42
}
'''

data = json.loads(response)

print(data["status"])
```

Output:

```text
ok
```

---

## Related Problems

- Read a JSON File
- Write a JSON File
- Pretty-Print JSON
- Convert a Dictionary to JSON
- Read a Text File

---

## Official Documentation

- `json.loads()`
- `json.load()`
- `json.JSONDecodeError`

Python Documentation:

- https://docs.python.org/3/library/json.html

---

## Summary

If you need to convert a JSON string into a Python dictionary, prefer:

```python
import json

data = json.loads(json_string)
```

If the JSON comes from a file:

```python
import json

with open("user.json", "r", encoding="utf-8") as file:
    data = json.load(file)
```

Remember:

```text
JSON object → Python dictionary
JSON array  → Python list
```

In modern Python code, `json.loads()` is generally the recommended approach for converting JSON strings into Python objects.