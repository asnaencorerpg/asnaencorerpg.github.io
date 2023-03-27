---
title: "%REM Function"

Id: REM_Function
TocParent: Functions_overview
TocOrder: 36


---

**%REM** [built-in function](Functions_overview.html) returns the remainder that results from dividing operands **n** by **m** . 

```

 ** *<result>*  = %REM**  (n,m)
```

### Parts

**n,m** 

Optional. Must be numeric values with zero decimal positions.


### Returns
** *<result>* ** contains the remainder that results from dividing **n** by **m** . If either operand is a packed, zoned, or binary numeric value, the result is packed numeric. If either operand is an integer numeric value, the result is integer. Otherwise, the result is unsigned numeric. Float numeric operands are not allowed.. 

### Remarks
% **REM** and [%DIV](DIV.html) have the following relationship: 

%REM(A,B) = A - (%DIV(A,B) * B) 

The result in this case has the same sign as the dividend. If the operands are constants that can fit in 8-byte integer or unsigned fields, constant folding is applied to the built-in function. In this case, the % **REM** built-in function can be coded in the definition specifications. 

### Example

```
BEGSR Rem_Ex 
DclFld Name(A) Type(*ZONED) Len(5,0)
DclFld Name(B) Type(*ZONED) Len(5,0)
DclFld Name(Result) Type(*ZONED) Len(5,0) 
A = 123 
B = 27 
Result = %DIV (A,B) 
MsgBox Result 
Result = %Rem(A,B) 
MsgBox Result 
Result = %Rem (A,B) + %Div (A,B) 
MsgBox Result 
// Now, "Result" = 4, 15, and 19 
```

### See Also
[Built-in Function Overview](Functions_overview.html)

[%DIV](DIV_Function.html) 
