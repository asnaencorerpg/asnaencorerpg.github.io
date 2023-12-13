---
title: "%TRIML Function"

Id: TRIML_Function
TocParent: Functions_overview
TocOrder: 49


---

**%TRIML** [built-in function](Functions_overview.html) returns the given string less any leading blanks. 

```
%TRIML (String) 
        
```

### Parts

**String** 

Required. Can be character, graphic, or UCS-2 data. When specified as a parameter for a definition specification keyword, the string parameter must be a constant.


### Example

```

BEGSR TrimL_Ex
    DclConst Name(String) Value(" This is a test string.")
	ioField1.Text = %TrimL (String)
ENDSR
```

### See Also
[Built-in Function Overview](Functions_overview.html)

[%TRIM Function](TRIM_Function.html)

[%TRIMR Function](TRIMR_Function.html) 
