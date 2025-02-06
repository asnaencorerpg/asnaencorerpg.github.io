---
title: Hexadecimal Literals

Id: Hexadecimal_Literal
TocParent: aerLrfLiteralsMain
TocOrder: 3


---

Hexadecimal literals may be used to define unicode strings or numeric values using hexadecimal notation. ASCII or EBCDIC hexadecimal strings are not supported.

##### Unicode Strings

The format for unicode strings is `U"..."` where the string between quotes must have a length that is multiple of 4. Each group of 4 hex digits in the string represents the Unicode value of a character. For example, `U"00480065006C006C006F"` represents the string `"Hello"`.

##### Numeric Values

The format for numeric constants in hex is `H"..."`. Hex numeric constants are integer values, and the size of the integer depends on the number of digits within the quotes:

- 1 - 2 digits represent a byte value
- 3 - 4 digits represent an 2-byte integer value
- 5 - 8 digits represent a 4-byte integer value
- 9 - 16 digits represent an 8-byte integer value

For example, H"00000032" is the value 50 as a 4-byte integer, whereas H"0032" is the value 50 as a 2-byte integer.

### Example

```c
 MyString = "Hello" + U"0009" + "World"   // U"0009" is TAB character
 Number2 = Number1 + H"64"                // add 100 (64 in Hex) to Number1

 DclConst myTab value( U"0009")           // Tab constant

 DclConst myNumber value( H"7FFF")        // 32767
```

### See Also

[Character Literal](Character_Literal.html)

[Date Literal](Date_Literals.html)

[Time Literal](Time_Literals.html)

[TimeStamp Literal](Timestamp_Literals.html)

[Literals](ecrLrfLiteralsMain.html) 
