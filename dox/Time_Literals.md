---
title: Time Literal

Id: Time_Literals
TocParent: aerLrfLiteralsMain
TocOrder: 10


---

**Time** **literals** take the form **`T"HH.MM.SS"`** where: 

- **`T`** indicates that the literal is of type **`*Time`**.
- **`"HH.MM.SS"`** is a valid time in the ISO format (24-hour clock).
- **`HH`** - the hour (0-23).
- **`MM`** - the minute of the hour (0-59).
- **`SS`** - the second of the minute (0-59).

### Remarks
**`HH.MM.SS`** must be enclosed by double-quote characters (") (see [Examples](#examples) below).

All digits are significant numeric decimal characters, e.g., for `HH` the sixth hour must be specified as `06`.

### Examples
`T"05:10:00"`

`T"22:39:59"`


### See Also
[Numeric Literal](Numeric_Literal.html)

[Hexadecimal Literal](Hexadecimal_Literal.html)

[Date Literal](Date_Literals.html)

[Character Literal](Character_Literal.html)

[TimeStamp Literal](Timestamp_Literals.html)

[Time Data Type](Time_Data_Type.html)

[Literals](ecrLrfLiteralsMain.html) 
