---
title: "%BOOL Function"

Id: BOOL_Function
TocParent: Functions_overview
TocOrder: 1


---

**BOOL** [built-in function](Functions_overview.html) returns the boolean value of **True** or **False** . 

```
%BOOL  (value)
```

### Remarks
Returns boolean value as follows. 

- A negative or positive number is true and any value that contains zero is
                false.
- A string is false if it is zero-length or filled with zeroes only, and true if
                its length is greater than zero and non-zero characters are present.
- An object of a type other than the four basic types is converted to a boolean
                in a way that is dependent on that type.

### See Also
[Built-in Function Overview](Functions_overview.html) 
