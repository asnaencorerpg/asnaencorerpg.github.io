---
title: DataGateException Class

Id: aerLrfDataGateExceptionClass
TocParent: aerLrfRuntimeNamespace
TocOrder: 1


---

The DataGateException class contains the information for exception errors occurring during program execution. 

For alist of members of this class, see [DataGateException Members](aerLrfDataGateExceptionMembers.html). 

[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html) <br /> ASNA.VisualRPG.Runtime. **DataGateException** 

```
 <Serializable>
 **DataGateExceptions : ASNA.VisualRPG.Runtime.DataGateException** 
```

### Thread Safety
This type is safe for multithreaded operations.

### Remarks
A DataGateException class provides for access to the current exception errors during program execution. 

[CausingException](ToString_Method_DGEClass.html) returns the encapsulated **dgException,** which is of type **ASNA.DataGate.Common.dgException** . 

The [ToString](ToString_Method_DGEClass.html) method returns a string representation of the current exception, and the [DclFileName](ToString_Method_DGEClass.html) field returns the name of the file in which the exception error occurred. 

### Requirements
**Namespace:** ASNA.VisualRPG. Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG. Runtime .dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows Vista Business Edition, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)
[DataGateException Members](aerLrfDataGateExceptionMembers.html) 
