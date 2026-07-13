---
layout: default
title: Pretty-Print JSON
---

# Pretty-Print JSON

---

## Problem

I have JSON data.

For example:

```json
{"name":"Alice","age":30,"languages":["Python","JavaScript"]}
```

It is difficult to read because everything appears on a single line.

I want the JSON to be formatted with indentation and line breaks.

---

## Recommended Solution

Use the `indent` parameter when calling `json.dumps()`.

```python
import json

data = {
    "name": "Alice",
    "age": 30,
    "languages": [
        "Python",
        "JavaScript"
    ]
}

formatted_json = json.dumps(
    data,
    indent=4
)

print(formatted_json)
```

Output:

```json
{
    "name": "Alice",
    "age": 30,
    "languages": [
        "Python",
        "JavaScript"
    ]
}
```

---

## Why Use Pretty-Printed JSON?

Pretty-printed JSON is easier to:

- Read
- Debug
- Review
- Edit manually
- Include in documentation

Compare:

Compact JSON:

```json
{"name":"Alice","age":30}
```

Pretty-printed JSON:

```json
{
    "name": "Alice",
    "age": 30
}
```

The second version is much easier for humans to understand.

---

## What Does json.dumps() Do?

`json.dumps()` converts Python objects into a JSON string.

Example:

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

Adding `indent=4` formats the output for readability.

---

## Common Indentation Values

Two spaces:

```python
json.dumps(data, indent=2)
```

Output:

```json
{
  "name": "Alice",
  "age": 30
}
```

Four spaces:

```python
json.dumps(data, indent=4)
```

Output:

```json
{
    "name": "Alice",
    "age": 30
}
```

Four spaces are commonly used in Python projects.

---

## Pretty-Printing JSON from a File

You can load JSON from a file and display it in a readable format.

```python
import json

with open("user.json", "r", encoding="utf-8") as file:
    data = json.load(file)

print(
    json.dumps(
        data,
        indent=4
    )
)
```

This is useful when inspecting configuration files or API responses.

---

## Writing Pretty-Printed JSON to a File

Use the `indent` parameter with `json.dump()`.

```python
import json

with open("user.json", "w", encoding="utf-8") as file:
    json.dump(
        data,
        file,
        indent=4
    )
```

The resulting file will be easy to read and edit.

---

## Preserving Unicode Characters

If your data contains non-English characters, use:

```python
import json

print(
    json.dumps(
        data,
        indent=4,
        ensure_ascii=False
    )
)
```

Example:

```python
{
    "name": "Jørgen"
}
```

Without `ensure_ascii=False`, some characters may be escaped.

---

## Sorting Keys

Sometimes you want JSON keys to appear in alphabetical order.

```python
import json

print(
    json.dumps(
        data,
        indent=4,
        sort_keys=True
    )
)
```

Output:

```json
{
    "age": 30,
    "name": "Alice"
}
```

This can make comparisons between files easier.

---

## When Would I Use This?

Common situations include:

- Debugging JSON data
- Reading API responses
- Creating configuration files
- Exporting application data
- Documentation examples
- Logging structured data

Example:

```python
import json

print(
    json.dumps(
        response_data,
        indent=4
    )
)
```

---

## Related Problems

- Read a JSON File
- Write a JSON File
- Convert JSON to a Dictionary
- Convert a Dictionary to JSON
- Read a Text File

---

## Official Documentation

- `json.dumps()`
- `json.dump()`

Python Documentation:

- https://docs.python.org/3/library/json.html

---

## Summary

If you need readable JSON output, prefer:

```python
import json

formatted_json = json.dumps(
    data,
    indent=4
)

print(formatted_json)
```

To write formatted JSON to a file:

```python
import json

with open("user.json", "w", encoding="utf-8") as file:
    json.dump(
        data,
        file,
        indent=4
    )
```

Pretty-printing JSON makes it easier to inspect, debug, and maintain JSON data.