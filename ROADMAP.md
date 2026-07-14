# easier-python-docs - ROADMAP

Find Python solutions by problem, not by module.

## Philosophy

This roadmap is intentionally lightweight.

It is not a checklist that must be completed.

It is a prioritization guide.

The goal is not:

- document everything
- cover all of Python
- create a complete reference

The goal is:

- reduce discovery friction
- help people find Pythonic solutions faster
- connect real-world problems to the right Python APIs

A page is most valuable when it solves a problem many Python developers regularly search for.

---

## 🔍 Discovery First

This project optimizes for discovery.

Many developers know Python probably contains a solution.

What they often do not know is:

- which API provides it
- which module contains it
- what the functionality is called

The project exists to reduce that discovery friction.

---

## 🎯 Current Focus

The current priority is:

1. Complete remaining Tier 1 pages
2. Expand coverage of common Python tasks
3. Improve cross-linking between related pages
4. Validate usefulness during real Python work

The goal right now is not:

- designing advanced navigation
- implementing search
- documenting edge cases
- covering every Python feature

The goal is to build a practical collection of high-frequency Python solutions.

---

## 📚 Current Coverage

### Filesystem

✅ 15 pages completed

### JSON

✅ 5 pages completed

### Strings

🚧 Not started

### Lists

🚧 Not started

### Dictionaries

🚧 Not started

### Dates and Times

🚧 Not started

### Environment Variables

🚧 Not started

### Subprocesses

🚧 Not started

### Command Line Applications

🚧 Not started

---

## ✅ Completed

### Filesystem

- Join paths
- Get current directory
- Check if a file exists
- Read a text file
- Write a text file
- Append to a text file
- List files in a directory
- Find files recursively
- Create a directory
- Check if a directory exists
- Get absolute path
- Get file name from path
- Get file extension
- Get parent directory
- Resolve relative paths

### JSON

- Read a JSON file
- Write a JSON file
- Pretty-print JSON
- Convert JSON to a dictionary
- Convert a dictionary to JSON

### Strings

- Split a string
- Join strings
- Replace text
- Remove whitespace
- Check if text contains a substring

## Lists

- Sort a list
- Remove duplicates

### Data Files

- Read a CSV file

---

# 🥇 Tier 1 — High-Frequency Problems

These are problems that many Python developers encounter regularly.

This tier should receive the majority of attention.

## Strings

- Check if text starts with a value
- Check if text ends with a value

## Lists

- Add an item to a list
- Remove an item from a list
- Find an item in a list
- Filter a list

## Dictionaries

- Get a value by key
- Add a key/value pair
- Update a value
- Check if a key exists
- Get a default value

## Filesystem

- Copy a file
- Move a file
- Rename a file
- Delete a file

## Dates and Times

- Get current date
- Get current datetime
- Format a date
- Parse a date string

## Environment Variables

- Read an environment variable
- Provide a default value
- Check whether an environment variable exists

## Subprocesses

- Run a command
- Capture command output

## Command Line Applications

- Read command-line arguments
- Accept flags
- Display help text

---

# 🥈 Tier 2 — Common but Less Frequent Problems

Useful tasks that developers encounter occasionally.

## Filesystem

- Create nested directories
- Create an empty file
- Get file size
- Get file modification time
- Delete a directory
- Rename a directory
- List only files
- List only directories

## Strings

- Convert to uppercase
- Convert to lowercase
- Count occurrences of text
- Pad a string
- Truncate a string

## Lists

- Reverse a list
- Loop through a list
- Flatten nested lists

## Dictionaries

- Delete a key
- Merge dictionaries
- Loop through a dictionary

## Dates and Times

- Calculate days between dates
- Add days to a date

## Subprocesses

- Check command exit status
- Pass arguments to a command

## Command Line Applications

- Accept positional arguments
- Read input from a user
- Prompt for confirmation

---

# 🥉 Tier 3 — Nice-to-Have Problems

These pages are useful but should generally be written only when:

- personally needed
- repeatedly searched for
- naturally connected to existing pages

## Filesystem

- Find files by extension
- Find newest file
- Find largest file
- Search for files matching a pattern

## Environment Variables

- Load variables from a .env file

---

## 🌱 Future Categories

These categories may eventually be added if they continue to align with the project's philosophy.

### Data Files

- Write a CSV file
- Read a TOML file
- Write a TOML file
- Read a YAML file
- Write a YAML file

### Testing

- Write a simple test
- Run tests with pytest
- Check expected exceptions

### Iteration

- Loop through a dictionary
- Loop with an index
- Group values
- Enumerate items

### Maybe Later

Only pursue these if they continue to align with the project's focus on common Python problems.

#### HTTP Requests

- Send a GET request
- Send a POST request
- Add request headers
- Parse a JSON response

---

## 💡 New Page Rule

A page is probably worth creating when:

- I have searched for it multiple times
- It solves a practical Python problem
- The solution can be explained on a single page
- There is a clear recommended solution
- It naturally links to official Python documentation

A useful rule of thumb:

> If I would search for it, it is probably a good easier-python-docs page.

---

## 🧭 Priority Rule

When choosing the next page to write:

1. Tier 1 always beats Tier 2.
2. Tier 2 always beats Tier 3.
3. Real-world usefulness beats completeness.
4. Discovery value beats technical depth.

The goal is not to document everything.

The goal is to help people find the right Python solution faster.
