---
title: "%DECH Function"

Id: DECH_Function
TocParent: Functions_overview
TocOrder: 8


---

**%DECH** [built-in function](Functions_overview.html) <span style="LETTER-SPACING: -0.25pt" />is the same as [%DEC](DEC_Function.html), except that if the expression is a decimal or float value, half adjust is applied to the value of the expression when converting to the desired precision. No message is issued if half adjust cannot be performed. 

```
%DECH  ( Numeric or Character Expression ,{ Precision, Decimal Places }) 
```

### Parts

**Numeric or Character Expression** 

Required. Contains the numeric or character expression in which to convert to packed decimal format.


**Precision, Decimal Places** 

Required. Precision and decimal places must be numeric literals, named constants that represent numeric literals, or built-in functions with a numeric value known at compile-time.


### Remarks
Unlike **%DEC** , all three parameters are required.

### Example

```
BEGSR Dech_Ex
  DclFld  Name( A )         Type( *ZONED ) Len( 9, 5 )
  DclFld  Name( B )         Type( *ZONED ) Len( 9, 5 )
  DclFld  Name( C))         Type( *ZONED ) Len( 9, 6 )
  DclFld  Name( Result1 )   Type( *ZONED ) Len( 9, 5 )
  DclFld  Name( Result2 )   Type( *ZONED ) Len( 7, 5 )
  DclFld  Name( Result3 )   Type( *ZONED ) Len( 8, 5 )

  A = 1234.567
  B = 73.73442
  C = 123.456789

  Result1 = %DEC( A ) + 0.011
  MsgBox Result1
  Result2 = %DEC( B, 5, 0 )
  MsgBox Result2
  Result3 = %DECH( C, 5, 2 )
  MsgBox Result3

  // The value of Result1 is now 1234.57800
  // The value of Result2 is now 73.00000
  // The value of Result3 is now 123.46000
ENDSR  
```

### See Also
[Built-in Function Overview](Functions_overview.html)

[%DEC Function](DEC_Function.html) 
