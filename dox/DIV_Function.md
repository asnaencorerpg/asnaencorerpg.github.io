---
title: "%DIV Function"

Id: DIV_Function
TocParent: Functions_overview
TocOrder: 12


---

**%DIV** [built-in function](Functions_overview.html) returns the integer portion of the quotient that results from dividing operands **N** by **M** . 

```

 **%DIV** ( **N,M** )
```

### Parts

**N,M** 

Required. Must be numeric values with zero decimal positions.

- If either operand is a packed, zoned, or binary numeric value, the result is packed numeric.
- If either operand is an integer numeric value, the result is integer. Otherwise, the result is unsigned numeric.
- Float numeric operands are not allowed.


### Remarks
% **DIV** and [%REM](REM_Function.html) built-in function have the following relationship: 

%REM(A,B) = A - (%DIV(A,B) * B) 

If the operands are constants that can fit in 8-byte integer or unsigned fields, constant folding is applied to the built-in function. In this case, %REM can be coded in the definition specifications. 

### Example

```
BEGSR Div_Ex 
DclFld Name(A) Type(*ZONED) Len(5,0)
DclFld Name(B) Type(*ZONED) Len(5,0)
DclFld Name(Result) Type(*ZONED) Len(5,0)

A = 123
B = 27

Result = %DIV (A,B)
MsgBox Result

Result = %Rem (A,B) 
MsgBox Result 

Result = %Rem (A,B) + %Div (A,B) 
MsgBox Result

//Now, "Result" = 4, 15, and 19 

ENDSR
```

### See Also
[Built-in Function Overview](Functions_overview.html)

[%REM Function](REM_Function.html) 
