---
title: DataGateException.CausingException Field

Id: aerLrfCausingExceptionFieldDataGateExceptionClass
TocParent: aerLrfDataGateExceptionFields
TocOrder: 0


---

**CausingException** returns the encapsulated **dgException** . 

```
 **CausingException (ASNA.DataGate.Common.dgException)** 
```

### Remarks
CausingException returns the encapsulated dgException, which is of type **ASNA.DataGate.Common.dgException** . 

The [ToString](ToString_Method_DGEClass.html) method also returns the errors that caused **CausingException** , along with the declared file name ([DclFileName](ecrLrfDclFileNameFieldDataGateExceptionClass.html) field). 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows Vista Business Edition, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](ecrLrfRuntimeNamespace.html)

[DataGateException Class](ecrLrfDataGateExceptionClass.html)

[DataGateException Members](ecrLrfDataGateExceptionMembers.html)

[DclFileName Field](ecrLrfDclFileNameFieldDataGateExceptionClass.html)

[ToString Method](ToString_Method_DGEClass.html) 
