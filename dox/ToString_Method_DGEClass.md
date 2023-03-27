---
title: DataGateException.ToString Method

Id: ToString_Method_DGEClass
TocParent: aerLrfDataGateExceptionMethods
TocOrder: 5


---

**ToString** returns a string representation of the current exception. 

```
 **ToString ()** 
        
```

### Remarks
The string returned by the **ToString** method contains the declared file name (DclFileName) and the errors that caused ([CausingException](aerLrfCausingExceptionFieldDataGateExceptionClass.html)) an exception during application execution. **CausingException** is of type **ASNA.DataGate.Common.dgException** . 

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)

[DataGateException Class](aerLrfDataGateExceptionClass.html)

[DataGateException Members](aerLrfDataGateExceptionMembers.html)

[CausingException Field](aerLrfCausingExceptionFieldDataGateExceptionClass.html) 
