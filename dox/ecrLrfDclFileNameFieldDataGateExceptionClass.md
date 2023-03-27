---
title: DataGateException.DclFileName Field

Id: aerLrfDclFileNameFieldDataGateExceptionClass
TocParent: aerLrfDataGateExceptionFields
TocOrder: 1


---

**DclFileName** returns the name of the file where the exception occurred. 

```
 **DclFileName (string)**     
```

### Remarks
The string returned by **DclFileName** contains the name of the file in which the exception error occurred. 

See [CausingException](ecrLrfCausingExceptionMethodDataGateExceptionClass.html) for the encapsulated exception during application execution. **CausingException** is of type **ASNA.DataGate.Common.dgException** . 

### Requirements
**Namespace:** ASNA.VisualRPG. Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG. Runtime .dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](ecrLrfRuntimeNamespace.html)

[DataGateException Class](ecrLrfDataGateExceptionClass.html)

[DataGateException Members](ecrLrfDataGateExceptionMembers.html)

[CausingException Field](ecrLrfCausingExceptionMethodDataGateExceptionClass.html) 
