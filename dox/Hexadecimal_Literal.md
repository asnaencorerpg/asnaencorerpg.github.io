---
title: Hexadecimal Literal

Id: Hexadecimal_Literal
TocParent: aerLrfLiteralsMain
TocOrder: 3


---

**Hexadecimal** **literals** may be used to define unicode string (U) and numeric (X) values. U"x1x2...xn" and X"x1x2…xn" can only contain the characters A-F, a-f, and 0-9. 

**Unicode** **literals** take the form U"Xxxx…Yyyy" where 4 bytes are given to represent a single unicode character. 

### Example
<dl class="Code" />
        
```
 Mystring = "Hello" + U"0009" + "World"   // U"0009" is TAB character
 Number2 = Number1 + X"64"    		  // add 100 to Number1

 DclConst myTab value( U"0009")     	  // Tab constant

 DclConst myNumber value( H"7FFF")        // 32767
```

### Remarks
Double quotes will be parsed the same way, so <code>U"0009" = U"0009".</code>

The syntax: H"&lt;hex digits&gt;" is not supported.

### See Also
[Character Literal](Character_Literal.html)
[Date Literal](Date_Literals.html)
[Time Literal](Time_Literals.html)
[TimeStamp Literal](Timestamp_Literals.html)
[Literals](aerLrfLiteralsMain.html) 
