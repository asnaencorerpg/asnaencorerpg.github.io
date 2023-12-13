---
title: "%INT Function"

Id: INT_Function
TocParent: Functions_overview
TocOrder: 23


---

**%INT** [built-in function](Functions_overview.html) converts the value of the numeric expression to integer. 

```
%INT (NumericExpression) 
        
```

### Parts

**NumericExpression** 

Required. The numeric expression to convert.


### Remarks
Any decimal digits are truncated. This built-in function may only be used in expressions. % **INT** can be used to truncate the decimal positions from a float or decimal value allowing it to be used as an array index. 

### Example

```

BEGSR Int_Ex
   DclFld Name( A )       Type( *ZONED ) Len( 7,3 )
   DclFld Name( B )       Type( *ZONED ) Len( 7,5 )
   DclFld Name( C )       Type( *ZONED ) Len( 7,3 )
   DclFld Name( Result1 ) Type( *ZONED ) Len( 9,5 )
   DclFld Name( Result2 ) Type( *ZONED ) Len( 7,5 )
   DclFld Name( Result3 ) Type( *ZONED ) Len( 8,5 )

   A = 1234.567
   B = 73.73442 
   C = 128.789

   Result1 = %Int ( A ) + 0.011
   Result2 = %Int ( B )
   Result3 = %Inth ( C )

   MsgBox Result1
   MsgBox Result2
   MsgBox Result3

   //The value of "Result1" is now 1234.01100
   //The value of "Result2" is now 73.00000   
   //The value of "Result3" is now 124.00000
ENDSR
```

### See Also
[Built-in Function Overview](Functions_overview.html)

[%INTH Function](INTH_Function.html) 
