# Round-Module
A Roblox module I made that can be used to round numbers with decimals.

Disclaimer
=========
You cannot use this module to turn a regular number with a decimal into a whole number unless the number is something like **7.96** where the final output
would be 8 as a whole number. Just use ``math.floor()``. Maybe in future updates ill update it to do that.

Usage
====
You simply put the number as the first parameter and for the second parameter, you put the n-th place after the decimal point.

Example:
```
local CMath = require((...).CMath)
local decimalNumber = 93.5468
local newNumber = CMath.Round(decimalNumber, 2) --2 places after the decimal point(100ths place)
print(newNumber)
-- It would print 93.55
```
