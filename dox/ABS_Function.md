---
title: "%ABS Function"

Id: ABS_Function
TocParent: Functions_overview
TocOrder: 0


---

**%ABS** [built-in function](Functions_overview.html) returns the absolute value of the numeric expression specified as the parameter. 

```
 %ABS(NumericExpression)
```

### Parts

**NumericExpression** 

Required. Numeric expression can be any valid numeric expression.

- If the value of the numeric expression is non-negative, the value is returned unchanged.
- If the value is negative, the value returned is the value of the expression but with the negative sign removed.


### Remarks
For date, time, or timestamp data, the returned value includes any separator characters. The format and separators of the result are the same as that of the parameter.

### See Also
[Built-in Function Overview](Functions_overview.html) 
