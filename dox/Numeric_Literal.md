---
title: Numeric Literal

Id: Numeric_Literal
TocParent: aerLrfLiteralsMain
TocOrder: 4


---

**Numeric literals** are constant numeric values that take the form [+/-]nnn[.nnn] where the +/- is optional, the nnn's are numerics (0-9) and the [.nnn] decimal portion is also optional. 

**Integers** are entered:

- <code>&lt;nnn&gt;S </code>: short number (16-bit integer)
- <code>&lt;nnn&gt;I</code> : integer number (32-bit integer)
- <code>&lt;nnn&gt;L</code> : long number (64-bit integer)
- Examples: 123s,
                3i, 97L, etc.

**Fixed Decimals** are entered:

- <code>&lt;nnn&gt; </code>: fixed decimal of size (&lt;digits&gt;, 0 )
- <code>&lt;nnn&gt;.</code> : fixed decimal of size (&lt;digits&gt;, 0 )
- <code>.&lt;nnn&gt;</code> : fixed decimal of size (&lt;digits&gt;, &lt;digits&gt;)
- <code>&lt;nnn&gt;.&lt;nnn&gt;</code> : fixed decimal of size (&lt;total digits&gt;, &lt;right hand digits&gt; )
- Examples: 9 (1, 0), 34. (2, 0), .6512 (4, 4),
                764.45 (5, 2)

**Floating Point** numbers are entered:

<code>&lt;nnn&gt;.&lt;nnn&gt;E&lt;sign&gt;&lt;nnn&gt;</code> : depending on the number magnitude the compiler creates either a single precision or a double precision floating point constant. The <code>&lt;sign&gt;</code> is optional. The syntax of the left hand side of the E follows the rules for fixed decimals 

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
