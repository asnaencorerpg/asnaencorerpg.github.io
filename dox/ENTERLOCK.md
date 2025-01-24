---
title: ENTERLOCK

Id: ENTERLOCK
TocParent: aerLrfOpCodesMain
TocOrder: 970


---

Locks an object for serializing access in multithreaded applications. 

```
ENTERLOCK 
Object (expression)
```

### Parameters

**Object** 

Optional. If given, Object must be an expression that evaluates to an object (an instance of a reference type). Instances of value types are not allowed. The default value depends on where in the program the **EnterLock** appears. 

- If it's in the body of an instance method, then the default value is ***This** .

- If it's in the body of a shared method, then the default value is ***typeof(<current class>).** This ensures serialization at a coarse level.


### Remarks
ENTERLOCK routines allow a programmer to protect segments of code for serial access in multithreaded applications. 

An **ENTERLOCK** routines must end with an [EXITLOCK](EXITLOCK.html).

### See Also
[EXITLOCK](EXITLOCK.html) 
