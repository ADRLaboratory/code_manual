---
title: Style Guide
layout: default
parent: Python
nav_order: 2
---

# Python Style Guide
{: .no_toc }

The ADR Laboratory mostly follows [PEP 8], [PEP 257], and [PEP 484] for basic Python code styling.

Here are some highlights:
- TOC
{:toc}

----

## Indentation

Indents should use 4 spaces per indentation level.

If using a tab, make sure your text editor actually converts it into 4 spaces, and doesn't use a tab character (ASCII code 9).

```py
# Correct:
def some_function(foo):
    if foo:
        print('Hi')
```

```py
# Incorrect:
def some_function(foo):
  if foo:               # Two spaces
           print('Hi')  # Any other number of spaces
```

----

## Continuation lines

The maximum line length is 79 characters. Docstrings and comments should be limited to 72 characters per line.

Wrap long lines of code using Python's implied line continuation inside parentheses, brackets, and braces.

```py
def long_function_name(param_1, param_2, param_3,
                       param_4):
    long_list_name = [param_1, param_2,
                      param_3, param_4]
    long_set_name = {param_1,
                     param_2,
                     param_3,
                     param_4}
```

Line breaks should occur before binary operations. Preferably wrap expressions in parentheses rather than using backslashes (`\`).

```py
# Correct:
total = (value_A + value_B
         - (value_C * value_D)
         + value_E)
```

```py
# Preferably don't do this:
total = value_A + value_B \
        - (value_C * value_D) \
        + value_E
```

----

## Blank lines

Remove extra white space from any blank lines.

Surround top-level function and class definitions with two blank lines.

Method definitions inside a class are surrounded by a single blank line.

Use blank lines within functions to indicate logical sections.

Include a blank line at the end of a Python file.

----

## Imports

Imports should usually be on separate lines.

```py
# Correct:
import os
import sys
```

```py
# Incorrect:
import os, sys
```

When using `from`, it is okay to list imports from the same directory in the same line.

```py
# Okay:
from compas.geometry import Point, Line
```

Group imports in the following order, with a blank line between each group:

1. Standard library imports
2. Related third party imports
3. Local application/library specific imports

----

## String quotes

While not specified in [PEP 8], ADR only uses single-quoted strings.

You can use double quotes `"` within a single-quoted string without escaping it.

```py
string = 'They say there is "no need" to escape these quotes.'
```

See more about best practices with string formatting [here](python_best_practices.html#F-strings).

----

## Whitespace

Avoid trailing whitespace anywhere in the code (white space after the end of a line).

Always surround binary operators with a single space on either side:
- Assignment (`=`)
- Augmented assigment (`+=`, `-=`, etc.)
- Comparisons (`==`, `<`, `>`, `!=`, `<=`, `>=`, `in`, `not in`, `is`, `is not`)
- Booleans (`and`, `or`, `not`)

Avoid extraneous whitespace elsewhere.

----

## Comments

Don't write contradictory, unhelpful, or unnecessary comments!

Comments should be complete English sentences with the first word capitalized, unless the first word is an identifier starting with a lower case letter.

Block and inline comments start with a `#` and a single space.

Inline comments should be separated from the statement with at least two spaces.

---

## Docstrings

Docstring styling is outlined in [PEP 257]. See [Best Practices] for more details on how to write docstrings at ADR.

----

## Naming conventions

### Class names
{: .no_toc }

Class names use a `CapitalizedWords` convention (capitalize first letter of each word).

### Function and variable names
{: .no_toc }

Both functions and variables use a `lower_case_with_underscores` convention.

If a function or variable is intended for "internal use" (e.g., private), use a `_single_leading_underscore`.

### Constants
{: .no_toc }

Constants use an `UPPER_CASE_WITH_UNDERSCORES` convention.

----

## Function annotations

Semantics for function annotations are discussed in [PEP 484].

Functions should use annotations wherever possible. For example:

```py
def do_something(name: str, variable: int) -> int:
    variable += 1
    print(f'Hi {name}, the variable now has value {variable}')
    return variable
```


[PEP 8]: https://peps.python.org/pep-0008/
[PEP 257]: https://peps.python.org/pep-0257/
[PEP 484]: https://peps.python.org/pep-0484/
[Best Practices]: python_best_practices.html
