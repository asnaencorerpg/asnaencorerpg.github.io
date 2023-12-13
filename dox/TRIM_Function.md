---
title: "%TRIM Function"

Id: TRIM_Function
TocParent: Functions_overview
TocOrder: 48


---

**%TRIM** [built-in function](Functions_overview.html) returns the given string less any leading and trailing blanks. 

```
%TRIM (String) 
        
```

### Parts

**String** 

Required. Can be character, graphic, or UCS-2 data. When specified as a parameter for a definition specification keyword, the string parameter must be a constant.


### Example

```

BEGSR Trim_Ex
    DclConst Name(String) Value(" This is a test string. ")
    ioField1.Text = %Trim (String)
ENDSR
```

### See Also
[Built-in Function Overview](Functions_overview.html)

[%TRIML Function](TRIML_Function.html)

[%TRIMR Function](TRIMR_Function.html) 
