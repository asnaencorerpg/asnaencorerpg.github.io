---
title: Variable Names

Id: Variable_Names
TocParent: aerLrfVariablesMain


---

One of the convenient features of Encore RPG is the automatic assignment of a program or externally defined variable to a *ControlName* .Value where *ControlName* and the program/externally defined variable name is the same. There are some <u>limitations</u> to variable usage of this type for arithmetic operations and as key fields for I/O operations. 

The Value property of an IOField control is <u>always</u> a string variable; i.e., Type (*CHAR). 

Although the *ControlName* definition of such a field is a string, the data is automatically converted to the externally defined field type and implicitly [MOVE](MOVE.html)'d to the field for purposes of database I/O. 

Conversely, a numerically defined external field is automatically converted to a string and implicitly **MOVE** 'd to the *ControlName* .Value of the same name. For example, when a record is read with numeric fields, Encore RPG automatically converts the value to a string and **MOVE** 's that string value into *ControlName* . The rules defined within the **EditCode** , **NumericLength** and **Decimals** properties apply. 

Because such fields are now string values, care must be taken when using these values for arithmetic operations. The general rule of thumb is that these fields may ** *not* ** be used as F1 and F2 in the [ADD](ADD.html), [DIV](DIV.html), [MULT](MULT.html), [SQRT](SQRT.html), and [SUB](SUB.html) arithmetic operations. F2 reference in [ZADD](ZADD.html) and [ZSUB](Z_SUB.html) is permitted. **In all cases, they may be referenced in Result.** 

For the same reason, care must be taken when using these values for keys for I/O operations like [CHAIN](CHAIN.html), [READ](READ.html), [SETLL](SETLL.html), [SETGT](SETGT.html). Packed and Binary keys must be separately defined for such operations. 

### See Also
[MOVE](MOVE.html)
[ADD](ADD.html)
[CHAIN](CHAIN.html)
[DIV](DIV.html)
[MULT](MULT.html)
[READ](READ.html)
[SETGT](SETGT.html)
[SETLL](SETLL.html)
[SQRT](SQRT.html)
[SUB](SUB.html) 
