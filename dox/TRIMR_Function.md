---
title: "%TRIMR Function"

Id: TRIMR_Function
TocParent: Functions_overview
TocOrder: 50


---

**%TRIMR** [built-in function](Functions_overview.html) returns the given string less any trailing blanks. 

```

 **%TRIMR (String)** 
        
```

### Parts

**String** 

Required. Can be character, graphic, or UCS-2 data. When specified as a parameter for a definition specification keyword, the string parameter must be a constant.


### Example

```

BEGSR CommandButton7 Click
    DclConst Name(String) Value("This is a test string. ")
    ioField1.Text = %TrimR (String)
ENDSR
```

### See Also
[Built-in Function Overview](Functions_overview.html)
[%TRIM Function](TRIM_Function.html)
[%TRIML Function](TRIML_Function.html) 
