---
title: IsEof Property

Id: IsEofPropertyDbFileClass
TocParent: aerLrfDBFilePropertiesMain
TocOrder: 1


---

Returns **True** when a file input operation results in **End-of-File** being reached. 

```
 *DBFile* 
 **.IsEof** 
 *[=boolean]*  
```

### Property Value
Boolean. Returns a **True** or **False** indicating if End-of-File has been reached. 

### Remarks
**IsEof** applies to the [READ](READ.html), [READC](READC.html), [READE](READE.html), [READP](READP.html), [READPE](READPE.html), [READRANGE](READRANGE.html) commands. 

**IsEof** is similar to the [%EOF](EOF_Function.html) built-in function, except that it relates to the operation for a file, specifically. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](ecrLrfRuntimeNamespace.html)

[DBFile Class](ecrLrfDBFileClass.html)

[DBFile Class Members](ecrLrfDBFileMembers.html)

[DCLDISKFILE](DCLDISKFILE.html)

[%EOF](EOF_Function.html) 
