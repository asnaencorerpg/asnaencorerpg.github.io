---
title: "%INTH Function"

Id: INTH_Function
TocParent: Functions_overview
TocOrder: 24


---

**INTH** [built-in function](Functions_overview.html) is the same as [%INT](INT_Function.html), except that if the numeric expression is a decimal or float value, half-adjust is applied to the value of the numeric expression when converting to integer type. 

```
%INTH (NumericExpression) 
        
```

### Parameters

**NumericExpression** 

Required. The numeric expression to convert.


### Remarks
No message is issued if half-adjust cannot be performed. 

### Example

```
BEGSR Inth_Ex
   DclFld Name(A)          Type(*ZONED) Len(7,3)
   DclFld Name(B)          Type(*ZONED) Len(7,5)
   DclFld Name(C)          Type(*ZONED) Len(7,3)
   DclFld Name(Result1)    Type(*ZONED) Len(9,5)
   DclFld Name(Result2)    Type(*ZONED) Len(7,5)
   DclFld Name(Result3)    Type(*ZONED) Len(8,5)

   A = 1234.567
   B = 73.7344
   C = 123.789

   Result1 = %Int (A) + 0.011
   Result2 = %Int (B)
   Result3 = %Inth(C)

   MsgBox Result1
   MsgBox Result2
   MsgBox Result3

   // The value of "Result1" is now 1234.01100
   // The value of "Result2" is now 73.00000
   // The value of "Result3" is now 124.00000
ENDSR
```

### See Also
[Built-in Function Overview](Functions_overview.html)

[%INT](INT_Function.html) 
