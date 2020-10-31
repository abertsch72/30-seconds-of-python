---
title: from_roman_numeral
tags: math,string,intermediate
---

Converts a valid roman numeral to its arabic number representation.
Accepts valid roman numerals with values 1-3999 inclusive (the non-expanded roman numeral system).

- Creates a dictionary mapping 1 and 2-character roman numerals to numbers
- Uses while loop to iterate through the string, checking for 1 or 2 character matches
- Sums the number representations of all matches

```py
def from_roman_numeral(roman):
  lookup = {
    'M': 1000,
    'CM': 900,
    'D': 500,
    'CD': 400,
    'C': 100,
    'XC': 90,
    'L': 50,
    'XL': 40,
    'X': 10,
    'IX': 9,
    'V': 5,
    'IV': 4,
    'I': 1
  }

  num = 0Looks
  index = 0
  while index < len(roman) - 1:
      if lookup.get(roman[index:index+2], None):
          num += lookup.get(roman[index:index+2])
          index += 2
      else:
          num += lookup.get(roman[index], 0)
          index += 1
  num += lookup.get(index, 0)

  return num
```

```py
from_roman_numeral("MMMCMXCIX") # 3999
from_roman_numeral("IV") # 4
```
