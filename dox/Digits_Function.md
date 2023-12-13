---
title: "%DIGITS Function"

Id: Digits_Function
TocParent: Functions_overview
TocOrder: 11


---

<span style="FONT-WEIGHT: bold">%DIGITS</span> [built-in function](Functions_overview.html) can be used to get and set digits of a Fixed Decimal Numeric. When getting, the digits are returned as a decimal number and when used for setting should be assigned a decimal expression. 

```
%DIGITS (Source, Start, Length )
```

### Parts

** *Source* ** 

Required. Must be a Fixed Decimal Numeric (*zoned, *packed, or *binary) from which the digits are extracted.


** *Start* ** 

Required. Represents the starting position from where to extract the digits of the fixed decimal. The starting position must be greater than zero.


***Length*** 

Required. Represents the number of digits to be extracted from the ***Source*** parameter.


### Remarks
**%Digits** can also be used to replace digits of a fixed decimal numeric when used as a result of an assignment expression. **%Digits** returns a decimal representing the number of digits, hence if the digits start with a 0, that 0 will not be a part of the number returned. 

### Example

```
BEGSR Digits_Ex
   DclFld Name(Phone) Type (*Packed) Len( 10, 0) INZ (2105551212)

   ioField1.Number = %Digits (Phone, 3, 7) //55512 ( 055512 as a valid decimal is 55512 )
ENDSR
```

### See Also
[Built-in Function Overview](Functions_overview.html)

[EVAL](EVAL.html) 
