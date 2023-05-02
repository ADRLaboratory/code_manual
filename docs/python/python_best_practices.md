---
title: Best Practices
layout: default
parent: Python
nav_order: 3
---

# Python Best Practices

## F-strings

Use literal string interpolation, or formatted strings (f-strings) in your code for clean, legible combinations of strings and variables.

Learn more about f-strings in [PEP 498].

```py
name_list = ['Arash', 'Salma', 'Alireza', 'Daniel']
index = 2
print(f'The name at index number {index} is {name_list[index]}!')
```

```
The name at index number 2 is Alireza!
```


[PEP 498]: https://peps.python.org/pep-0498/
