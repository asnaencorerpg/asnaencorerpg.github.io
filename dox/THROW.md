---
title: THROW

Id: THROW
TocParent: aerLrfOpCodesMain
TocOrder: 1540


---

**THROW** is used to signal the occurrence of an anomalous situation (exception) during the program execution. 

```
THROW 
 Exception  (Type of class filter)
```

### Parts

**Exception** 

Required. The exception object. Provides information about the exception to be thrown.


### Remarks
The Throw statement throws an exception that you can handle with structured exception-handling code (Try...Catch...Finally) or unstructured exception-handling code (If %Error). 

**Example** 

```

Throw *new System.Exception( "Invalid property value") 
```

### See Also
[CATCH](CATCH.html)

[FINALLY](FINALLY.html)

[TRY](TRY.html)

[TRY...CATCH...FINALLY](TRYCATCHFINALLY.html) 
