---
title: "%CHAR Function"

Id: CHAR_Function
TocParent: Functions_overview
TocOrder: 2


---

**%CHAR** [built-in function](Functions_overview.html) converts the value of the expression from numeric, date, time or timestamp data to type character. 

```
%CHAR 
 (Expression) 
        
```

### Parameters

**Expression** 

Required. Can be any valid numeric expression. If the parameter is a constant, the conversion will be done at compile time.


### Remarks
For date, time, or timestamp data, the returned value includes any separator characters. The format and separators of the result are the same as that of the parameter. 

The **%CHAR** command **cannot** accept *BOOLEAN and *IND data types. 

### See Also
[Built-in Function Overview](Functions_overview.html) 
