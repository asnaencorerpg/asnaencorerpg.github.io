---
title: IsFound Property

Id: IsFoundPropertyDbFileClass
TocParent: aerLrfDBFilePropertiesMain
TocOrder: 3


---

Returns **True** when a keyed file record I/O operation results in a record being found. 

```

 *DBFile* 
 **.IsFound** 
 *[=boolean]*  
```

### Property Value
Boolean. Returns a True or False indicating if a keyed file record I/O operation results in a record being found. 

### Remarks
**IsFound** applies to [CHAIN](CHAIN.html), [DELETE](DELETE.html), [DELETERANGE](DELETERANGE.html), [READRAND](READRAND.html), [READRANGE](READRANGE.html), [SETLL](SETLL.html), [SETGT](SETGT.html) commands. 

**IsFound** is equivalent to the [%FOUND](FOUND_Function.html) built-in function. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows Server 2012, Windows Server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)
[DBFile Class](aerLrfDBFileClass.html)
[DBFile Class Members](aerLrfDBFileMembers.html)
[DCLDISKFILE](DCLDISKFILE.html)
[%FOUND](FOUND_Function.html) <br /> <br /> 
