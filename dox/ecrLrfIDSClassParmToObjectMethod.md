---
title: IDS.ParmToObject Method

Id: aerLrfIDSClassParmToObjectMethod
TocParent: aerLrfIDSClassMethods
TocOrder: 4


---

**ParmToObject** passes the data structure as an **output** parameter on the remote call. 

```
 *ids* . **ParmToObject** (program, indices, dim) 
```

### Parameters

*program* 

An instance of ASNA.DataGate.Client.As400Program object.


*indices* 

Integer. The number of indecies in the data structure.


*dim* 

Integer. The number of data structure fields.


### Remarks
**ParmToObject** passes the data structure as an **output** parameter on the remote call. 

### Requirements
**Namespace:** ASNA.VisualRPG. Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG. Runtime .dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

#### See Also
[ASNA.VisualRPG.Runtime](ecrLrfRuntimeNamespace.html)

[IDS Interface](ecrLrfIDSClass.html)

[DCLDS](DCLDS.html) 
