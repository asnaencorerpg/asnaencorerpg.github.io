---
title: Timestamp Literal

Id: Timestamp_Literals
TocParent: aerLrfLiteralsMain
TocOrder: 15


---

**Timestamp literals** take the form **Z"yyyy-mm-dd-hh.mm.ss.mmmmmm"** where: 

- **Z** indicates that the literal is of type Timestamp.
- **yyyy-mm-dd** is a valid date (year-month-day).
- **hh.mm.ss.mmmmmm** is a valid time (hours.minutes.seconds.microseconds).

### Remarks
**yyyy-mm-dd-hh.mm.ss.mmmmmm** is enclosed by apostrophes. 

Microseconds are optional and if not specified will default to zeros.

### Example
Z"1997-07-22-10.15.05.000030"

### See Also
[Numeric Literal](Numeric_Literal.html)

[Hexadecimal Literal](Hexadecimal_Literal.html)

[Date Literal](Date_Literals.html)

[Time Literal](Time_Literals.html)

[Character Literal](Character_Literal.html)

[Timestamp Data Type](Timestamp_Data_Type.html)

[Literals](ecrLrfLiteralsMain.html) 
