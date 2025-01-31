---
title: Timestamp Literal

Id: Timestamp_Literals
TocParent: aerLrfLiteralsMain
TocOrder: 15


---

**Timestamp literals** take the form **`Z"yyyy-mm-dd-hh.mm.ss.mmmmmm"`** where: 

- **`Z`** indicates that the literal is of type **\*Timestamp**.
- **`yyyy-mm-dd`** is a valid Gregorian calendar date (year, month of year, day of month).
- **`hh.mm.ss.mmmmmm`** is a valid 24-hour time of day (hour, minute, second, and optional microsecond).

### Remarks
**`yyyy-mm-dd-hh.mm.ss.mmmmmm`** must be enclosed by double-quote characters (see [Examples](#examples) below).

All digits are significant numeric decimal characters, e.g., for `yyyy`, year "614" must be specified as `0614`.

The month is a number between `01` and `12` inclusive.

The day is a number between `01` an XX inclusive, where 'XX' is the total number of days in the specified month of the specified year.

The hour is a number between `00` and `23` inclusive.

The second is a number between `00` and `59` inclusive.

The microsecond is optional and if not specified will default to `000000`.

### Examples
`Z"2024-07-22-17.15.05.000030"`

`Z"1970-01-01-00.00.00"`

### See Also
[Numeric Literal](Numeric_Literal.html)

[Hexadecimal Literal](Hexadecimal_Literal.html)

[Date Literal](Date_Literals.html)

[Time Literal](Time_Literals.html)

[Character Literal](Character_Literal.html)

[Timestamp Data Type](Timestamp_Data_Type.html)

[Literals](ecrLrfLiteralsMain.html) 
