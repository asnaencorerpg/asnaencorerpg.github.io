---
title: "%EDITFLT Function"

Id: EDITFLT_Function
TocParent: Functions_overview
TocOrder: 14


---

**%EDITFLT** [built-in function](Functions_overview.html) converts the value of the numeric expression to the character external display representation of float. The result is either 14 or 23 characters. If the argument is a 4-byte float field, the result is 14 characters. Otherwise, it is 23 characters. 

```
%EDITFLT (NumericExpression) 
        
```

### Parameters

**NumericExpression** 

Required. If specified as a parameter to a definition specification keyword, the parameter must be a numeric literal, float literal, or numeric value constant name or built-in function. 

When specified in an expression, constant folding is applied if the numeric expression has a constant value.


### Example

```
BEGSR
  DclFld Name(A) Type(*ZONED) Len(5,0)<br />  DclFld Name(Result) Type(*String)

  A = 50000
  Result = "Float value is " + %EditFlt (A) + "."
  MsgBox Result

// The value of "Result" is "Float value is +5.000000e+004."
ENDSR
```

### See Also
[Built-in Function Overview](Functions_overview.html)

