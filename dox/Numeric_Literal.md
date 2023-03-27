---
title: Numeric Literal

Id: Numeric_Literal
TocParent: aerLrfLiteralsMain
TocOrder: 4


---

**Numeric literals** are constant numeric values that take the form [+/-]nnn[.nnn] where the +/- is optional, the nnn's are numerics (0-9) and the [.nnn] decimal portion is also optional. 

**Integers** are entered:

- ```<nnn>S ```: short number (16-bit integer)
- ```<nnn>I``` : integer number (32-bit integer)
- ```<nnn>L``` : long number (64-bit integer)
- Examples: 123s,
                3i, 97L, etc.

**Fixed Decimals** are entered:

- ```<nnn> ```: fixed decimal of size (<digits>, 0 )
- ```<nnn>.``` : fixed decimal of size (<digits>, 0 )
- ```.<nnn>``` : fixed decimal of size (<digits>, <digits>)
- ```<nnn>.<nnn>``` : fixed decimal of size (<total digits>, <right hand digits> )
- Examples: 9 (1, 0), 34. (2, 0), .6512 (4, 4),
                764.45 (5, 2)

**Floating Point** numbers are entered:

```<nnn>.<nnn>E<sign><nnn>``` : depending on the number magnitude the compiler creates either a single precision or a double precision floating point constant. The ```<sign>``` is optional. The syntax of the left hand side of the E follows the rules for fixed decimals 

### Remarks

- The **+** or **-** sign must be the leftmost character, if present. An unsigned literal is treated as a positive number.
- Blanks cannot appear in a numeric literal.
- The **.** character is used as a decimal point (e.g. -12.53 ).

### Example

```
 1.2, -45.6, +89.2         
```

### See Also
[Hexadecimal Literal](Hexadecimal_Literal.html)

[Date Literal](Date_Literals.html)

[Time Literal](Time_Literals.html)

[TimeStamp Literal](Timestamp_Literals.html)

[Literals](aerLrfLiteralsMain.html) 
