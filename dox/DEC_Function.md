---
title: "%DEC Function"

Id: DEC_Function
TocParent: Functions_overview
TocOrder: 7


---

**%DEC** [built-in function](Functions_overview.html) converts the value of the first parameter to packed decimal format. 

Note that the first parameter can be either a numeric or character expression and can specify a precision and decimal places, or it can be a date, time or timestamp; in which you can specify a format type. 

```
%DEC  ( Numeric or Character Expression  , {Precision, DecimalPlaces})   
```
        
```
%DEC  ( Date, Time or Timestamp   , {Format})

```

### Parts

**Expression** 

Required. Contains the expression in which to convert to packed decimal format.


When the first parameter is a numeric or character expression, the result has *precision* digits and *decimal places* decimal positions. The precision and decimal places must be numeric literals, named constants that represent numeric literals, or built-in functions with a numeric value known at compile-time.


**Precision, DecimalPlaces** 

Optional. Must be numeric or character expression. They may be omitted if the type of numeric expression is not float. If these parameters are omitted, the precision and decimal places are taken from the attributes of the numeric expression.


If the parameter is a character expression, the following rules apply: 

- The sign is optional. It can be "+" or "-". It can precede or follow the
                        numeric data.
- The decimal point is optional. It can be either a period or a comma.
- Blanks are allowed anywhere in the data. For example, " + 3 " is a valid
                        parameter.
- The second and third parameters are required.
- Floating point data, for example "1.2E6", is not allowed.


**Format** 

Optional. The optional format parameter specifies the format of the value returned. The converted decimal value will have the number of digits that a value of that format can have, and zero decimal positions. For example, if the first parameter is a date, and the format is *YMD, the decimal value will have six digits.


If this parameter is omitted, the format of the first parameter is used.


### Remarks
**%DEC**  is the same as [%DECH](DECH_Function.html),
        except that with % **DECH** , if the expression is a decimal or
        float value, half-adjust is applied to the value of numeric expression when
        converting to the desired precision.

### Example

```
BEGSR Dec_Ex
   DclFld Name( A )         Type( *ZONED ) Len( 9, 5 )  
   DclFld Name( B )         Type( *ZONED ) Len( 9, 5 ) 
   DclFld Name( C )         Type( *ZONED ) Len( 9, 6 ) 
   DclFld Name( Result1 )   Type( *ZONED ) Len( 9, 5 ) 
   DclFld Name( Result2 )   Type( *ZONED ) Len( 7, 5 )
   DclFld Name( Result3 )   Type( *ZONED ) Len( 8, 5 )

   A = 1234.567
   B = 73.73442
   C = 123.456789

   Result1 = %DEC(A) + 0.011
   MsgBox Result1
   Result2 = %DEC(B, 5, 0) 
   MsgBox Result2
   Result3 = %DECH(C, 5, 2)
   MsgBox Result3

 // The value of "Result1" is now 1234.57800
 // The value of "Result2" is now 73.00000
 // The value of "Result3" is now 123.46000
ENDSR
```

### See Also
[Built-in Function Overview](Functions_overview.html)

[%DECH Function](DECH_Function.html) 
