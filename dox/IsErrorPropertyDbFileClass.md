---
title: IsError Property

Id: IsErrorPropertyDbFileClass
TocParent: aerLrfDBFilePropertiesMain
TocOrder: 2


---

Returns **True** when an I/O operation results in an error condition. 

```

 *DBFile* 
 **.IsError** 
 *[=boolean]*  
```

### Property Value
Boolean. Returns a **True** or **False** indicating if an I/O operation results in an error condition. 

### Remarks
**IsError** applies to **all** file I/O commands except [CLOSE](CLOSE.html). 

IsError is similar to the [%ERROR](ERROR_Function.html) built-in function, except that it relates to the error operation for a file, specifically. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](ecrLrfRuntimeNamespace.html)

[DBFile Class](ecrLrfDBFileClass.html)

[DBFile Members](ecrLrfDBFileMembers.html)

[DCLDISKFILE](DCLDISKFILE.html)

[%ERROR](ERROR_Function.html) 
