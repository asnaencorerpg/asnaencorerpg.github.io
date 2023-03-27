---
title: IsEqual Property

Id: IsEqualPropertyDbFileClass
TocParent: aerLrfDBFilePropertiesMain
TocOrder: 2


---

Returns **True** when a keyed file **"Seek"** operation results in a record being found that matches the seek Key. 

```

 *DBFile* 
 **.IsEqual** 
 *[=boolean]*  
```

### Property Value
Boolean. Returns a **True** or **False** indicating whether a keyed file Seek operation results in a record being found that matches the seek Key. 

### Remarks
**IsEqual** applies to [SETLL](SETLL.html) command. 

**IsEqual** is equivalent to the [%EQUAL](EQUAL_Function.html) built-in function. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](ecrLrfRuntimeNamespace.html)

[DBFile Class](ecrLrfDBFileClass.html)

[DBFile Class Members](ecrLrfDBFileMembers.html)

[DCLDISKFILE](DCLDISKFILE.html)

[%EQUAL](EQUAL_Function.html) 
