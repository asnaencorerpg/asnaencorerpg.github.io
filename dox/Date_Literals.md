---
title: Date Literals

Id: Date_Literals
TocParent: aerLrfLiteralsMain
TocOrder: 2


---

**Date** **literals** take the form **`D"YYYY-MM-DD"`** where: 

- **`D`** indicates that the literal is of type **`*Date`**.
- **`YYYY-MM-DD`** represents a valid Gregorian calendar date in the `*ISO` format.
- **`YYYY`** is the year.
- **`MM`** is the month of the year.
- **`DD`** is the day of the month.

See [Date Formats](Date_Formats.html) for more information. 

### Remarks
**`YYYY-MM-DD`** must be enclosed by the double-quote character (").  See [Examples](#examples) below. 

All digits are significant numeric decimal characters, e.g., for `YYYY`, year "614" must be specified as `0614`.

The month is a number between `01` and `12` inclusive.

The day is a number between `01` an XX inclusive, where 'XX' is the total number of days in the specified month of the specified year.

### Examples
`D"1887-01-31"`

`D"1996-04-01"`

### See Also
[Character Literal](Character_Literal.html)

[Date Data Type](Date_Data_Type.html)

[Date Formats](Date_Formats.html)

[Hexadecimal Literal](Hexadecimal_Literal.html)

[Time Literal](Time_Literals.html)

[TimeStamp Literal](Timestamp_Literals.html)

[Literals](ecrLrfLiteralsMain.html) 
